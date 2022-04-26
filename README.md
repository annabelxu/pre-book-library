
# URL
URL=http://127.0.0.1:5000
URL=https://book-library-123.uc.r.appspot.com

# Homepage
curl http://127.0.0.1:5000

# Get all books data
curl http://127.0.0.1:5000/books

# Get books(with image) and isbn
curl http://127.0.0.1:5000/9781501124020

# Test 404
curl http://127.0.0.1:5000/http://127.0.0.1:5000/9781501124021

# Test 406
curl http://127.0.0.1:5000/http://127.0.0.1:5000/97815011240

# Post books(with image) and isbn
curl -X POST -H "Content-Type:multipart/form-data" -F "file=@cover1.png" -F "isbn=9781501124020"  -F "author=Ray Dalio" -F "language=English" -F "pages=592" -F "title=Principles" -F "year=2017" http://127.0.0.1:5000/books 

# Put books and isbn
curl -X PUT -d 'title=Principles&author=Ray Dalio&language=English&pages=592&year=2018' http://127.0.0.1:5000/books/9781501124020

# Delete books 
curl -X DELETE http://127.0.0.1:5000/books/9781501124020
