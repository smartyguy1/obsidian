We now have a list of words in worf_quote so the next step is to create a set of stop words to filter words_in_quote. For this we you'll need to focus on stop words in "english"


```python
import PyPDF2 as pdf
```


```python
bns = open('Downloads/bns2.pdf', 'rb')
```


```python
from PyPDF2 import PdfReader, PdfWriter, PdfMerger
```


```python
bns_read = PdfReader(bns)
```

This creates a reader object named `bns_read`

# Extract Text


```python
#extract text from a page
bns_read.pages[0].extract_text()
```




    '(i)\nTHE BHARATIYA NYAYA (SECOND) SANHITA, 2023\n—————\nARRANGEMENT OF CLAUSES\n—————\nCHAPTER IP\nRELIMINARY\nCLAUSES\n1. Short title, commencement and application.\n2. Definitions.\n3. General explanations.\nCHAPTER II\nOF PUNISHMENTS\n4. Punishments.\n5. Commutation of sentence.\n6. Fractions of terms of punishment.7. Sentence may be (in certain cases of imprisonment) wholly or partly rigorous or\nsimple.\n8. Amount of fine, liability in default of payment of fine, etc.9. Limit of punishment of offence made up of several offences.\n10. Punishment of person guilty of one of several offences,  judgment stating that it is\ndoubtful of which.\n11. Solitary confinement.12. Limit of solitary confinement.13. Enhanced punishment for certain offences after previous conviction.\nCHAPTER III\nG\nENERAL  EXCEPTIONS\n14. Act done by a person bound, or by mistake of fact believing himself bound, by law.15. Act of Judge when acting judicially.\n16. Act done pursuant to judgment or order of Court.\n17. Act done by a person justified, or by mistake of fact believing himself  justified, by\nlaw.\n18. Accident in doing a lawful act.19. Act likely to cause harm, but done without criminal intent, and to prevent other\nharm.\n20. Act of a child under seven years of age.\n21. Act of a child above seven and under twelve years of age of immature understanding.\n22. Act of a person of unsound mind.23. Act of a person incapable of judgment by reason of intoxication caused against his\nwill.AS INTRODUCED  IN LOK SABHA\nBill No. 173 of 2023'




```python
### Function to extract text from pdf
def get_text_from_pdf(pdf_path):
    pages1 = []
    with open(pdf_path, "rb") as file:
        pdf = PdfReader(file)
        for page in pdf.pages:
            text = page.extract_text()
            pages1.append(text)
        return pages1;
```

# Getting metadata


```python
info = bns_read.metadata
info
```




    {'/ModDate': "D:20231212203826+05'30'",
     '/Title': 'Bharatiya Nyaya (Second) Sanhita, 2023',
     '/Creator': 'PageMaker 6.5',
     '/CreationDate': "D:20231212074828+05'30'",
     '/Author': '',
     '/Producer': 'Acrobat Distiller 7.0 (Windows)',
     '/Subject': '',
     '/Keywords': ''}




```python
bns_read.metadata.title
```




    'Bharatiya Nyaya (Second) Sanhita, 2023'




```python
#create read object
reader = PdfReader(bns)
```


```python
#Prints number of pages
len(reader.pages)
```




    145




```python
#Write a function to get the metadata of a pdf
def get_pdf_metadata(pdf_file):
    with open(pdf_file, "rb") as f:
        reader = PdfReader(f)
        info = reader.metadata
    return info

get_pdf_metadata("Downloads/bns2.pdf")        
```




    {'/ModDate': "D:20231212203826+05'30'",
     '/Title': 'Bharatiya Nyaya (Second) Sanhita, 2023',
     '/Creator': 'PageMaker 6.5',
     '/CreationDate': "D:20231212074828+05'30'",
     '/Author': '',
     '/Producer': 'Acrobat Distiller 7.0 (Windows)',
     '/Subject': '',
     '/Keywords': ''}



We can also use `''.join(pages1)` to join all the strings into a single string

# How to split a pdf
- split into multiple pdfs
- split off the last page
- get pdf upto a particular page


```python
#Function to split pdf into multiple pages
import os
def split_pdf(pdf_path):
    with open(pdf_path, 'rb') as f:
        reader = PdfReader(f)
        #get all pages
        for i in range(0,3):
            writer = PdfWriter() #create a writer object **very important**
            writer.add_page(reader.pages[i])#add/embedding of the page
            
            filename = os.path.splitext(pdf_path)[0]
            output_filename = f'{filename}{i}.pdf'
            
            #save and compile to pdf
            with open(output_filename, 'wb') as out:
                writer.write(out)
            print("created a pdf:{}". format(output_filename))
```


```python
os.path.splitext('Downloads/bns2.pdf')
```




    ('Downloads/bns2', '.pdf')




```python
split_pdf('Downloads/bns2.pdf')
```

    created a pdf:Downloads/bns20.pdf
    created a pdf:Downloads/bns21.pdf
    created a pdf:Downloads/bns22.pdf



```python
#Split pdf upto a particular page
def get_pdf_upto(pdf_path, start_page:int=0, stop_page:int = 0):
    with open(pdf_path,'rb') as f:
        reader = PdfReader(f)
        writer = PdfWriter()
        for page in range(start_page, stop_page):
            selected_page = reader.pages[page]
            writer.add_page(selected_page) ##This takes the page object and copies it into the writer object
            filename = os.path.splitext(pdf_path)[0]
            output_filename = f'{filename}_from_{start_page}_to_{stop_page}.pdf'
        with open(output_filename, 'wb') as out:
            writer.write(out)
```


```python
get_pdf_upto('Downloads/bns2.pdf', 0,2) #Got my pages
```


```python
#Get last page of the given pdf
def get_last_pdf_page(pdf_path):
    with open(pdf_path, 'rb') as f:
        reader = PdfReader(f)
        writer = PdfWriter()
        last_page = len(reader.pages)-1
        selected_page = reader.pages[last_page]
        writer.add_page(selected_page)
        filename = os.path.splitext(pdf_path)[0]
        output_filename = f'{filename}_last.pdf'
        
        with open(output_filename, 'wb') as out:
            writer.write(out)
```


```python
get_last_pdf_page('Downloads/bns2.pdf') #Got the last page
```

# Merging Pdfs
- Get a list of pdfs
- PdfMerger(PdfFileMerger)


```python
def fetch_all_files(parent_folder: str):
    target_files = []
    for path, subdirs, files in os.walk(parent_folder):
        for name in files:
            if name.endswith('.pdf'):
                target_files.append(os.path.join(path, name))
    return target_files
```


```python
fetch_all_files('./Out')
```




    ['./Out/bns2_from_0_to_2.pdf', './Out/bns2_last.pdf']




```python
def merge_pdf(list_of_pdfs, output_filename='merged.pdf'):
    merger = PdfMerger()
    with open(output_filename, 'wb') as f:
        for file in list_of_pdfs:
            merger.append(file)
        merger.write(f)
```


```python
pdf_list = fetch_all_files('Out')
```


```python
merge_pdf(pdf_list)
```

# How to rotate a PDF Page


```python
def rotate_pdf(pdf_path, page_num:int=0, rotation:int=90):
    with open(pdf_path, 'rb') as f:
        
        reader = PdfReader(f)
        writer = PdfWriter()
        writer.add_page(reader.pages[page_num])
        
        #rotate
        writer.pages[0].rotate(rotation)
        
        filename = os.path.splitext(pdf_path)[0]
        output_filename = f'{filename}_{rotation}_done.pdf'
        
        with open(output_filename, 'wb') as out:
            writer.write(out)
        
        print(f"Rotated page {page_num} by {rotation} degrees")
```


```python
rotate_pdf('merged.pdf', 1)
```

    Rotated page 1 by 90 degrees

