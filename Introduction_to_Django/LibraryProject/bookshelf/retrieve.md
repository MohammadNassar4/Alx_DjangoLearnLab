retrieved_book = Book.objects.get(id=book.id)
print(f"Retrieved book: {retrieved_book.title} by {retrieved_book.author}, published in {retrieved_book.publication_year}")

<!-- Retrieved book: 1984 by George Orwell, published in 1949 -->