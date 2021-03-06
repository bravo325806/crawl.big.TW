# crawl.big.TW

### Configure Setting : 
Edit the file `bigTW/.env.example`, and save as `.env`.
```
cp .env.example .env
vim .env
```

### Python3 Requirement :
```
scrapy
pymysql
python-dotenv
```

### Create MySQL Table :
```
create table news (
    id int AUTO_INCREMENT, 
    kind text,
    title text,
    content text,
    img text,
    time text, 
    primary key(id)
)
```

* If you don't want to filter duplicate data from SQL, just comments out [this line](https://github.com/plusoneee/crawl.big.TW/blob/master/bigTW/pipelines.py#L35). like :

```python
def process_item(self, item, spider):
    # self.filter_repeat_data(item)
    return item
```

### How to RUN :
* Move into the project
```
cd bigTW
```
* RUN Scrapy 
```
scrapy crawl travel
```
* If you want a `.csv` output file:
```
scrapy crawl travel -o output.csv
```
