from bookshelf.models import Book
book = Book.objects.create(
    title = "1984",
    author = "George Orwell",
    publication_year = 1949)

retrieved_book = Book.objects.get(id=book.id)
print(f"Retrieved book: {retrieved_book.title} by {retrieved_book.author}, published in {retrieved_book.publication_year}")
<!-- Retrieved book: 1984 by George Orwell, published in 1949 -->

retrieved_book.title = "Nineteen Eighty-Four"
retrieved_book.save()
print(f"Updated book title: {retrieved_book.title}")
<!-- Updated book title: Nineteen Eighty-Four -->

book_id = retrieved_book.id
retrieved_book.delete()
print(f"Book with ID {book_id} has been deleted")
<!-- Book with ID 1 has been deleted -->

try:
    Book.objects.get(id=book_id)
except Book.DoesNotExist:
    print("Confirmed: Book successfully deleted from database")
<!-- Confirmed: Book successfully deleted from database -->