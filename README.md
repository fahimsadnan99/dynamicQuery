# dynamicQuery


  const axios = require('axios');

const queryObj = {
  searchTerm: 'apple',
  minPrice: 10,
  maxPrice: 50,
  sortBy: 'price',
  sortOrder: 'asc'
};

let queryString = '';

Object.keys(queryObj).forEach((key, index) => {
  const value = queryObj[key];

  if (value !== null && value !== undefined) {
    const prefix = index === 0 ? '?' : '&';
    queryString += `${prefix}${key}=${encodeURIComponent(value)}`;
  }
});

const query = `https://example.com/api/products${queryString}`;

axios.get(query)
  .then(response => {
    // handle response
  })
  .catch(error => {
    // handle error
  });
