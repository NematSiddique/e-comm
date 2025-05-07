### Step 1: Set Up the React Project

1. **Create a new React app** using Create React App:
   ```bash
   npx create-react-app my-ecommerce-app
   cd my-ecommerce-app
   ```

2. **Install necessary packages** (if needed):
   ```bash
   npm install react-router-dom
   ```

### Step 2: Project Structure

Organize your project structure as follows:

```
my-ecommerce-app/
├── public/
├── src/
│   ├── components/
│   │   ├── Loader.js
│   │   ├── ProductCard.js
│   │   ├── ToastNotification.js
│   ├── pages/
│   │   ├── LandingPage.js
│   │   ├── ProductDetailsPage.js
│   ├── App.js
│   ├── index.js
│   └── styles.css
```

### Step 3: Implement Components

#### 1. Loader Component

Create `Loader.js` in the `components` folder:

```jsx
// src/components/Loader.js
import React from 'react';

const Loader = () => {
    return (
        <div className="loader">
            <p>Loading...</p>
        </div>
    );
};

export default Loader;
```

#### 2. Product Card Component

Create `ProductCard.js` in the `components` folder:

```jsx
// src/components/ProductCard.js
import React from 'react';

const ProductCard = ({ product, onClick }) => {
    return (
        <div className="product-card" onClick={onClick}>
            <img src={product.image} alt={product.name} />
            <h3>{product.name}</h3>
            <p>${product.price}</p>
        </div>
    );
};

export default ProductCard;
```

#### 3. Toast Notification Component

Create `ToastNotification.js` in the `components` folder:

```jsx
// src/components/ToastNotification.js
import React from 'react';

const ToastNotification = ({ message, onClose }) => {
    return (
        <div className="toast-notification">
            <p>{message}</p>
            <button onClick={onClose}>Close</button>
        </div>
    );
};

export default ToastNotification;
```

### Step 4: Implement Pages

#### 1. Landing Page

Create `LandingPage.js` in the `pages` folder:

```jsx
// src/pages/LandingPage.js
import React, { useState } from 'react';
import ProductCard from '../components/ProductCard';
import Loader from '../components/Loader';

const LandingPage = () => {
    const [loading, setLoading] = useState(false);
    const [products, setProducts] = useState([]);
    const [searchTerm, setSearchTerm] = useState('');

    const handleSearch = () => {
        setLoading(true);
        // Simulate fetching products
        setTimeout(() => {
            // Replace with actual product fetching logic
            const fetchedProducts = [
                { id: 1, name: 'Product 1', price: 29.99, image: 'https://via.placeholder.com/150' },
                { id: 2, name: 'Product 2', price: 39.99, image: 'https://via.placeholder.com/150' },
            ];
            setProducts(fetchedProducts);
            setLoading(false);
        }, 1000);
    };

    return (
        <div>
            <h1>Landing Page</h1>
            <input
                type="text"
                placeholder="Search products..."
                value={searchTerm}
                onChange={(e) => setSearchTerm(e.target.value)}
            />
            <button onClick={handleSearch}>Search</button>
            {loading ? (
                <Loader />
            ) : (
                <div className="product-grid">
                    {products.map((product) => (
                        <ProductCard key={product.id} product={product} onClick={() => alert(`Clicked on ${product.name}`)} />
                    ))}
                </div>
            )}
        </div>
    );
};

export default LandingPage;
```

#### 2. Product Details Page

Create `ProductDetailsPage.js` in the `pages` folder:

```jsx
// src/pages/ProductDetailsPage.js
import React from 'react';

const ProductDetailsPage = ({ product }) => {
    return (
        <div>
            <h1>{product.name}</h1>
            <img src={product.image} alt={product.name} />
            <p>Price: ${product.price}</p>
            <p>Description: This is a detailed description of the product.</p>
        </div>
    );
};

export default ProductDetailsPage;
```

### Step 5: Set Up Routing in App.js

Modify `App.js` to include routing:

```jsx
// src/App.js
import React from 'react';
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';
import LandingPage from './pages/LandingPage';
import ProductDetailsPage from './pages/ProductDetailsPage';

const App = () => {
    return (
        <Router>
            <Switch>
                <Route path="/" exact component={LandingPage} />
                <Route path="/product/:id" component={ProductDetailsPage} />
            </Switch>
        </Router>
    );
};

export default App;
```

### Step 6: Add Basic Styles

You can add some basic styles in `styles.css`:

```css
/* src/styles.css */
body {
    font-family: Arial, sans-serif;
}

.product-grid {
    display: flex;
    gap: 20px;
}

.product-card {
    border: 1px solid #ccc;
    padding: 10px;
    cursor: pointer;
}

.loader {
    text-align: center;
}

.toast-notification {
    background-color: #f8d7da;
    color: #721c24;
    padding: 10px;
    margin: 10px 0;
}
```

### Step 7: Run the Application

Finally, run your application:

```bash
npm start
```

### Conclusion

You now have a basic React application with a landing page, product cards, a loader, and a product details page. You can expand upon this by adding more features, such as actual product fetching, state management, and more advanced styling.