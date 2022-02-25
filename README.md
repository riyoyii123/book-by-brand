# book-by-brand
Books on Amazon and Flipkart which can be joined using their ISBN numbers
pip install pandas
import pandas as pd
amazon_df=pd.read_csv('amazon.csv')
pd.isnull(amazon_df)
#data cleaning
amazon_book = amazon_df.rename(columns={'amazon_title':'Book Title', 'amazon_author':'Book Author','amazon_rating': 'Ratings','amazon_reviews count':'Reviews Count' ,'amazon_isbn-10': 'Isbn Number','amazon_price':'Price' })
amazon_book['Ratings'] = amazon_book.Ratings.str.replace('out of 5 stars','')
pd.set_option('display.max_rows', None)
amazon_book.at[379,'Ratings']='4.1'
amazon_book.loc[433]
amazon_book.at[433,'Ratings']='4.6'
amazon_book.at[433,'Reviews Count']='763'
