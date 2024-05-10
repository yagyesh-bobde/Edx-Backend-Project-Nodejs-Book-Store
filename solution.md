# Solution Response For the Final Project

### Q.1

```
[
    {
        "id": 1,
        "ISBN": "QB123",
        "title": "A Postman Theory",
        "author": "Robert James",
        "createdAt": "2024-05-10T11:15:45.160Z",
        "updatedAt": "2024-05-10T11:15:45.160Z"
    },
    {
        "id": 2,
        "ISBN": "QB223",
        "title": "A Postman Theory 2",
        "author": "Robert James 2",
        "createdAt": "2024-05-10T11:16:13.066Z",
        "updatedAt": "2024-05-10T11:16:13.066Z"
    },
    {
        "id": 3,
        "ISBN": "QB323",
        "title": "A Postman Theory 2",
        "author": "Robert James 2",
        "createdAt": "2024-05-10T11:16:16.233Z",
        "updatedAt": "2024-05-10T11:16:16.233Z"
    },
    {
        "id": 4,
        "ISBN": "QB323",
        "title": "A Postman Theory 3",
        "author": "Robert James 3",
        "createdAt": "2024-05-10T11:16:21.541Z",
        "updatedAt": "2024-05-10T11:16:21.541Z"
    }
]
```

## Q.2

```
{
    "message": "Books are Found!!",
    "foundBooks": [
        {
            "id": 1,
            "ISBN": "QB123",
            "title": "A Postman Theory",
            "author": "Robert James",
            "createdAt": "2024-05-10T11:15:45.160Z",
            "updatedAt": "2024-05-10T11:15:45.160Z"
        }
    ]
}
```

## Q.3

```
{
    "message": "Books are Found!!",
    "foundBooks": [
        {
            "id": 1,
            "ISBN": "QB123",
            "title": "A Postman Theory",
            "author": "Robert James",
            "createdAt": "2024-05-10T11:15:45.160Z",
            "updatedAt": "2024-05-10T11:15:45.160Z"
        }
    ]
}
```

## Q.4

```
{
    "message": "Books are Found!!",
    "foundBooks": [
        {
            "id": 2,
            "ISBN": "QB223",
            "title": "A Postman Theory 2",
            "author": "Robert James 2",
            "createdAt": "2024-05-10T11:16:13.066Z",
            "updatedAt": "2024-05-10T11:16:13.066Z"
        },
        {
            "id": 3,
            "ISBN": "QB323",
            "title": "A Postman Theory 2",
            "author": "Robert James 2",
            "createdAt": "2024-05-10T11:16:16.233Z",
            "updatedAt": "2024-05-10T11:16:16.233Z"
        }
    ]
}
```

## Q.5

```
{
    "message": "review found for this book",
    "bookReview": [
        {
            "review_text": "A fantastic book"
        }
    ]
}
```

## Q.6

```
{
    "message": "This user is already registered!"
}
```

## Q.7

```
{
    "message": "User logged in successfully!",
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2lkIjoyLCJ1c2VybmFtZSI6InVzZXIgbmV3ICIsImlhdCI6MTcxNTM0MjM5Mn0.8im-d9q7p7HbXUgY4UEZ58dTlkL-6k886PZtqRKXlSQ"
}
```

## Q.8

```
{
    "message": "Review added/updated successfully!"
}
```

## Q.9

```
{
    "message": "review deleted for that user successfully!"
}
```

## Q.10

```
export async function getAllBooks(req, res) {
  try {
    const books = await book.findAll();
    res.json(books);
  } catch (error) {
    res
      .status(500)
      .json({ message: "Internal Server Error!!", error: error.message });
  }
}
```

## Q.11

```
export async function getBooksByISBN(req, res) {
  try {
    const { ISBN } = req.body;

    if (!ISBN) {
      return res.json({ message: "Please, provide a valid ISBN Code!" });
    }

    const foundBooks = await book.findAll({ where: { ISBN } });
    if (foundBooks.length) {
      return res.json({ message: "Books are Found!!", foundBooks });
    }

    res.json({ message: "No book found with this ISBN Code!" });
  } catch (error) {
    res.status(500).json({ message: "Internal Server Error!!" });
  }
}
```

## Q.12

```
export async function getBooksByAuthor(req, res) {
  try {
    const { author } = req.body;

    if (!author) {
      return res.json({ message: "Please, provide a valid author name!" });
    }

    const foundBooks = await book.findAll({ where: { author } });
    if (foundBooks.length) {
      return res.json({ message: "Books are Found!!", foundBooks });
    }

    res.json({ message: "No book found with this author name!" });
  } catch (error) {
    res.status(500).json({ message: "Internal Server Error!!" });
  }
}
```

## Q.13

```

export async function getBooksByTitle(req, res) {
  try {
    const { title } = req.body;

    if (!title) {
      return res.json({ message: "Please, provide a valid title!" });
    }

    const foundBooks = await book.findAll({ where: { title } });
    if (foundBooks.length) {
      return res.json({ message: "Books are Found!!", foundBooks });
    }

    res.json({ message: "No book found with this title!" });
  } catch (error) {
    res.status(500).json({ message: "Internal Server Error!!" });
  }
}
```

## Q.14

```
https://github.com/yagyesh-bobde/Edx-Backend-Project-Nodejs-Book-Store
```
