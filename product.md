
## Brand

### List Brands

**Endpoint:** `/api/brands/`  
**Method:** GET  
**Description:** Retrieve a list of all brands.

**Query Parameters:**
- `brand_name` (string): Filter brands by name.

**Example Request:**
```bash
GET /api/brands/?brand_name=SearchKeyword
```

### Create Brand

**Endpoint:** `/api/brands/`  
**Method:** POST  
**Description:** Create a new brand.

**Required Fields:**
- `brand_name` (string): The name of the brand.
- `short_description` (text): A short description of the brand.

**JSON Data Example:**
```json
{
  "brand_name": "New Brand",
  "short_description": "A short description of the new brand."
}
```

### Retrieve Brand

**Endpoint:** `/api/brands/{brand_id}/`  
**Method:** GET  
**Description:** Retrieve details of a specific brand.

### Update Brand

**Endpoint:** `/api/brands/{brand_id}/`  
**Method:** PUT  
**Description:** Update details of a specific brand.

**Required Fields:**
- `brand_name` (string): The updated name of the brand.
- `short_description` (text): The updated short description of the brand.

**JSON Data Example:**
```json
{
  "brand_name": "Updated Brand",
  "short_description": "An updated short description."
}
```

### Delete Brand

**Endpoint:** `/api/brands/{brand_id}/`  
**Method:** DELETE  
**Description:** Delete a specific brand.

---

## Category

### List Categories

**Endpoint:** `/api/categories/`  
**Method:** GET  
**Description:** Retrieve a list of all categories.

**Query Parameters:**
- `category_name` (string): Filter categories by name.

**Example Request:**
```bash
GET /api/categories/?category_name=SearchKeyword
```

### Create Category

**Endpoint:** `/api/categories/`  
**Method:** POST  
**Description:** Create a new category.

**Required Fields:**
- `category_name` (string): The name of the category.
- `category_code` (string): The code assigned to the category.
- `description` (text): A description of the category.
- `brand` (integer): The ID of the associated brand.

**JSON Data Example:**
```json
{
  "category_name": "New Category",
  "category_code": "CAT001",
  "description": "A description of the new category.",
  "brand": 1
}
```

### Retrieve Category

**Endpoint:** `/api/categories/{category_id}/`  
**Method:** GET  
**Description:** Retrieve details of a specific category.

### Update Category

**Endpoint:** `/api/categories/{category_id}/`  
**Method:** PUT  
**Description:** Update details of a specific category.

**Required Fields:**
- `category_name` (string): The updated name of the category.
- `category_code` (string): The updated code assigned to the category.
- `description` (text): The updated description of the category.

**JSON Data Example:**
```json
{
  "category_name": "Updated Category",
  "category_code": "CAT002",
  "description": "An updated description."
}
```

### Delete Category

**Endpoint:** `/api/categories/{category_id}/`  
**Method:** DELETE  
**Description:** Delete a specific category.

---

## Subcategory

### List Subcategories

**Endpoint:** `/api/subcategories/`  
**Method:** GET  
**Description:** Retrieve a list of all subcategories.

**Query Parameters:**
- `subcategory_name` (string): Filter subcategories by name.

**Example Request:**
```bash
GET /api/subcategories/?subcategory_name=SearchKeyword
```

### Create Subcategory

**Endpoint:** `/api/subcategories/`  
**Method:** POST  
**Description:** Create a new subcategory.

**Required Fields:**
- `subcategory_name` (string): The name of the subcategory.
- `category` (integer): The ID of the associated category.

**JSON Data Example:**
```json
{
  "subcategory_name": "New Subcategory",
  "category": 1
}
```

### Retrieve Subcategory

**Endpoint:** `/api/subcategories/{subcategory_id}/`  
**Method:** GET  
**Description:** Retrieve details of a specific subcategory.

### Update Subcategory

**Endpoint:** `/api/subcategories/{subcategory_id}/`  
**Method:** PUT  
**Description:** Update details of a specific subcategory.

**Required Fields:**
- `subcategory_name` (string): The updated name of the subcategory.

**JSON Data Example:**
```json
{
  "subcategory_name": "Updated Subcategory"
}
```

### Delete Subcategory

**Endpoint:** `/api/subcategories/{subcategory_id}/`  
**Method:** DELETE  
**Description:** Delete a specific subcategory.

---

## Warranty

### List Warranties

**Endpoint:** `/api/warranties/`  
**Method:** GET  
**Description:** Retrieve a list of all warranties.

**Query Parameters:**
- `warranty_name` (string): Filter warranties by name.

**Example Request:**
```bash
GET /api/warranties/?warranty_name=SearchKeyword
```

### Create Warranty

**Endpoint:** `/api/warranties/`  
**Method:** POST  
**Description:** Create a new warranty.

**Required Fields:**
- `warranty_name` (string): The name of the warranty.
- `warranty_description` (text): A description of the warranty.
- `warranty_duration` (integer): The duration of the warranty.
- `warranty_duration_type` (integer): Choose from available duration types.

**JSON Data Example:**
```json
{
  "warranty_name": "New Warranty",
  "warranty_description": "A description of the new warranty.",
  "warranty_duration": 2,
  "warranty_duration_type": 1
}
```

### Retrieve Warranty

**Endpoint:** `/api/warranties/{warranty_id}/`  
**Method:** GET  
**Description:** Retrieve details of a specific warranty.

### Update Warranty

**Endpoint:** `/api/warranties/{warranty_id}/`  
**Method:** PUT  
**Description:** Update details of a specific warranty.

**Required Fields:**
- `warranty_name` (string): The updated name of the warranty.
- `warranty_description` (text): The updated description of the warranty.
- `warranty_duration` (integer): The updated duration of the warranty.

**JSON Data Example:**
```json


{
  "warranty_name": "Updated Warranty",
  "warranty_description": "An updated description.",
  "warranty_duration": 3
}
```

### Delete Warranty

**Endpoint:** `/api/warranties/{warranty_id}/`  
**Method:** DELETE  
**Description:** Delete a specific warranty.



## Stock API Documentation

### List Opening Stocks
- **URL:** `GET /api/openingstocks/`
- **Example:** `https://your-api-domain.com/api/openingstocks/`

### Get Opening Stock Details
- **URL:** `GET /api/openingstocks/<int:pk>/`
- **Example:** `https://your-api-domain.com/api/openingstocks/1/`

### Create Opening Stock
- **URL:** `POST /api/openingstocks/`
- **Example:** `https://your-api-domain.com/api/openingstocks/`
- **Request Body:**

```json
{
  "product": 123,  // ID of the associated AddProduct instance
  "variation": 456,  // ID of the associated Variations instance (if applicable)
  "remaining_quantity": 15,
  "unit_cost": 25.99,
  "subtotal": 389.85,
  "date": "2024-01-02",  // Formatted as YYYY-MM-DD
  "note": "Initial stock for new product launch",
  "lot_number": "ABC12345",
  "product_name": "Widget X"
}
```

**Explanation:**

- **Field names:** Match exactly with the model's field names.
- **Data types:**
    - `product` and `variation`: Integers representing the IDs of related instances.
    - `remaining_quantity`: Positive integer.
    - `unit_cost` and `subtotal`: Decimal numbers with two decimal places.
    - `date`: String formatted as YYYY-MM-DD.
    - `note`: Text string.
    - `lot_number`: String up to any characters.
    - `product_name`: String up to 36 characters.





## Barcode Generator API Documentation

### Generate Barcode
Generate barcode images with product information.

#### URL
```
POST /api/generate-barcode/
```

#### Parameters
- **product_id** (integer, required): The ID of the product for which the barcode is generated.
- **include_product** (boolean, optional): Include product name in the barcode details. Default is `False`.
- **include_business** (boolean, optional): Include business name in the barcode details. Default is `False`.
- **include_variations** (boolean, optional): Include product variations in the barcode details. Default is `False`.
- **include_price** (boolean, optional): Include product price in the barcode details. Default is `False`.
- **include_packing_date** (boolean, optional): Include packing date in the barcode details. Default is `False`.
- **packing_date** (string, optional): The packing date of the product.
- **label_no** (integer, optional): Number of labels to generate. Default is `1`.

#### Example
```json
{
    "product_id": 1,
    "include_product": true,
    "include_business": true,
    "include_variations": true,
    "include_price": true,
    "include_packing_date": true,
    "packing_date": "2024-01-03",
    "label_no": 3
}
```

#### Response
```json
{
    "message": "Image saved successfully.",
    "image_urls": [
        "https://your-api-domain.com/media/barcode/product12345BARCODE.png",
        "https://your-api-domain.com/media/barcode/product12345BARCODE.png",
        "https://your-api-domain.com/media/barcode/product12345BARCODE.png"
    ]
}
```
