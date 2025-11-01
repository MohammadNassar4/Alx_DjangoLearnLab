book_id = retrieved_book.id
retrieved_book.delete()
print(f"Book with ID {book_id} has been deleted")
<!-- Book with ID 1 has been deleted -->

try:
    Book.objects.get(id=book_id)
except Book.DoesNotExist:
    print("Confirmed: Book successfully deleted from database")
<!-- Confirmed: Book successfully deleted from database -->