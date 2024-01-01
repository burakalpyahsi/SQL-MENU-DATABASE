CREATE DATABASE IF NOT EXISTS RestaurantMenu;

USE RestaurantMenu;

CREATE TABLE IF NOT EXISTS AllOfTheRestaurantMenu(
    ID INT AUTO_INCREMENT PRIMARY KEY,
    Name VARCHAR(255) NOT NULL,
    Ingredients TEXT NOT NULL,
    CookingMethod VARCHAR(50) NOT NULL,
    Price DECIMAL(10,2)
);

    
CREATE TABLE IF NOT EXISTS Foods (
    ID INT AUTO_INCREMENT PRIMARY KEY,
    MenuID INT,
    Name VARCHAR(255) NOT NULL,
    Ingredients TEXT NOT NULL,
    CookingMethod VARCHAR(50) NOT NULL,
    FOREIGN KEY (MenuID) REFERENCES AllOfTheRestaurantMenu(ID)
);   
    
CREATE TABLE IF NOT EXISTS MainDishes (
    ID INT AUTO_INCREMENT PRIMARY KEY,
    FoodsID INT,
    Name VARCHAR(255) NOT NULL,
    Ingredients TEXT NOT NULL,
    CookingMethod VARCHAR(50) NOT NULL,
    FOREIGN KEY (FoodsID) REFERENCES Foods(ID)
);

CREATE TABLE IF NOT EXISTS VegetarianDishes (
    ID INT AUTO_INCREMENT PRIMARY KEY,
    FoodsID INT,
    Name VARCHAR(255) NOT NULL,
    Ingredients TEXT NOT NULL,
    CookingMethod VARCHAR(50) NOT NULL,
    FOREIGN KEY (FoodsID) REFERENCES Foods(ID)
);

CREATE TABLE IF NOT EXISTS VeganDishes (
    ID INT AUTO_INCREMENT PRIMARY KEY,
    FoodsID INT,
    Name VARCHAR(255) NOT NULL,
    Ingredients TEXT NOT NULL,
    CookingMethod VARCHAR(50) NOT NULL,
    FOREIGN KEY (FoodsID) REFERENCES Foods(ID)
);

CREATE TABLE IF NOT EXISTS NonHalalDishes (
    ID INT AUTO_INCREMENT PRIMARY KEY,
    FoodsID INT,
    Name VARCHAR(255) NOT NULL,
    Ingredients TEXT NOT NULL,
    CookingMethod VARCHAR(50) NOT NULL,
    FOREIGN KEY (FoodsID) REFERENCES Foods(ID)
);

CREATE TABLE IF NOT EXISTS Soups (
     ID INT AUTO_INCREMENT PRIMARY KEY,
    FoodsID INT,
    Name VARCHAR(255) NOT NULL,
    Ingredients TEXT NOT NULL,
    CookingMethod VARCHAR(50) NOT NULL,
    FOREIGN KEY (FoodsID) REFERENCES Foods(ID)
);

CREATE TABLE IF NOT EXISTS Desserts (
    ID INT AUTO_INCREMENT PRIMARY KEY,
    FoodsID INT,
    Name VARCHAR(255) NOT NULL,
    Ingredients TEXT NOT NULL,
    CookingMethod VARCHAR(50) NOT NULL,
    FOREIGN KEY (FoodsID) REFERENCES Foods(ID)
);

CREATE TABLE IF NOT EXISTS Breads (
     ID INT AUTO_INCREMENT PRIMARY KEY,
    FoodsID INT,
    Name VARCHAR(255) NOT NULL,
    Ingredients TEXT NOT NULL,
    CookingMethod VARCHAR(50) NOT NULL,
    FOREIGN KEY (FoodsID) REFERENCES Foods(ID)
);

CREATE TABLE IF NOT EXISTS Salads (
     ID INT AUTO_INCREMENT PRIMARY KEY,
    FoodsID INT,
    Name VARCHAR(255) NOT NULL,
    Ingredients TEXT NOT NULL,
    CookingMethod VARCHAR(50) NOT NULL,
    FOREIGN KEY (FoodsID) REFERENCES Foods(ID)
);

CREATE TABLE IF NOT EXISTS BEVERAGES(
	ID INT AUTO_INCREMENT PRIMARY KEY,
    MenuID INT,
    Name VARCHAR(255) NOT NULL,
    Ingredients TEXT NOT NULL,
    ServingStyle VARCHAR(50) NOT NULL,
    FOREIGN KEY (MenuID) REFERENCES AllOfTheRestaurantMenu(ID)
    );


CREATE TABLE IF NOT EXISTS AlcoholicBeverages (
    ID INT AUTO_INCREMENT PRIMARY KEY,
    BeverageID INT,
    Name VARCHAR(255) NOT NULL,
    Ingredients TEXT NOT NULL,
    ServingStyle VARCHAR(50) NOT NULL,
    FOREIGN KEY (BeverageID) REFERENCES BEVERAGES(ID)
);

CREATE TABLE IF NOT EXISTS NonAlcoholicBeverages (
    ID INT AUTO_INCREMENT PRIMARY KEY,
    BeverageID INT,
    Name VARCHAR(255) NOT NULL,
    Ingredients TEXT NOT NULL,
    ServingStyle VARCHAR(50) NOT NULL,
    FOREIGN KEY (BeverageID) REFERENCES BEVERAGES(ID)
);

INSERT INTO AllOfTheRestaurantMenu (Name, Ingredients, CookingMethod)
VALUES
('Grilled Chicken Skewers', 'Chicken meat, olive oil, spices', 'Grilling'),
('Vegetable Lamb Casserole', 'Lamb meat, vegetables, tomato sauce', 'Oven Casserole'),
('Fish Pan', 'Sea bass, lemon, fresh herbs', 'Oven Baking'),
('Cauliflower Patties', 'Cauliflower, bulgur, onion, spices', 'Boiling, Frying'),
('Lentil Patties', 'Red lentils, bulgur, onion, spices', 'Boiling'),
('Chicken Chickpea Dish', 'Chicken meat, chickpeas, onion, garlic, spices', 'Boiling in Pot'),
('Grilled Meatballs', 'Beef minced meat, spices, onion', 'Grilling'),
('Vegetable Baked Potato', 'Potatoes, vegetables, cheddar cheese', 'Baking in Oven'),
('Olive Oil Zucchini Dolma', 'Zucchini, rice, onion, olive oil', 'Baking in Oven'),
('Chicken Baked Potato', 'Chicken, potatoes, corn, peas', 'Baking in Oven'),
('Spinach Pie', 'Spinach, phyllo dough, feta cheese', 'Baking in Oven'),
('Vegetable Stew', 'Vegetables, meat broth, spices', 'Boiling in Pot'),
('Sultans Delight', 'Lamb meat, eggplant, bechamel sauce', 'Baking in Oven'),
('Lamb Tandoori', 'Lamb meat, spices, yogurt', 'Baking in Oven'),
('Sautéed Mushrooms', 'Mushrooms, onion, olive oil', 'Sautéing'),
('Quinoa Salad', 'Quinoa, vegetables, olive oil', 'Mixing'),
('Lentil Vegan Meatballs', 'Red lentils, vegetables, spices', 'Frying'),
('Baked Vegetables', 'Broccoli, carrot, zucchini, olive oil', 'Baking in Oven'),
('Chickpea Vegan Curry', 'Chickpeas, vegetables, coconut milk', 'Sautéing'),
('Vegan Pizza', 'Pizza dough, tomato sauce, vegetables', 'Baking in Oven'),
('Seasonal Vegetarian Risotto', 'Arborio rice, vegetables, parmesan cheese', 'Mixing'),
('Spinach and Cheese Pastry', 'Spinach, feta cheese, phyllo dough', 'Baking in Oven'),
('Baked Potato', 'Potatoes, cheddar cheese, butter', 'Baking in Oven'),
('Vegetarian Noodle Stir-Fry', 'Noodles, vegetables, soy sauce', 'Sautéing'),
('Olive Oil Grape Leaves', 'Grape leaves filling, olive oil', 'Baking in Oven'),
('Wine-Infused Beef Stew', 'Beef, red wine, vegetables, spices', 'Slow Cooking'),
('Braised Lamb in Red Wine Sauce', 'Lamb, red wine, herbs, garlic', 'Braising'),
('Chicken Marsala', 'Chicken, Marsala wine, mushrooms, butter', 'Sautéing'),
('Pork Tenderloin with Port Wine Sauce', 'Pork tenderloin, port wine, shallots, thyme', 'Roasting'),
('Beef Bourguignon', 'Beef, red wine, onions, carrots, mushrooms', 'Slow Cooking'),
('Lentil Soup', 'Red lentils, onion, carrot', 'Boiling'),
('Tarhana Soup', 'Tarhana, yogurt, fresh herbs', 'Boiling'),
('Tomato Soup', 'Tomatoes, onion, fresh herbs', 'Boiling'),
('Head and Trotter Soup', 'Lamb head, chickpeas, spices', 'Boiling'),
('Ezo Gelin Soup', 'Red lentils, bulgur, onion, tomato paste', 'Boiling'),
('Yogurt Yayla Soup', 'Yogurt, flour, butter, mint', 'Boiling'),
('Vegetable Soup', 'Vegetables, meat broth, spices', 'Boiling'),
('Zucchini Soup', 'Zucchini, onion, milk', 'Boiling'),
('Vermicelli Soup', 'Vermicelli, chicken broth, spices', 'Boiling'),
('Bone Broth Soup', 'Bone broth, vegetables, spices', 'Boiling'),
('Chicken Soup', 'Chicken broth, vermicelli, fresh herbs', 'Boiling'),
('Bean Soup', 'Dry beans, onion, tomatoes', 'Boiling'),
('Mushroom Soup', 'Mushrooms, onion, cream', 'Boiling, Blending Smooth'),
('Lamb Meat Soup', 'Lamb meat, vegetables, spices', 'Boiling'),
('Zucchini Cartilage Soup', 'Zucchini, cartilage, chicken broth', 'Boiling'),
('Baklava', 'Phyllo dough, walnuts, sugar, butter, syrup', 'Baking in Oven'),
('Rice Pudding', 'Rice, milk, sugar, vanilla', 'Baking in Oven'),
('Kazandibi', 'Milk, sugar, rice flour, butter', 'Cooking on Stove by Stirring'),
('Revani', 'Flour, sugar, eggs, semolina', 'Baking in Oven'),
('Kadaif', 'Kadaif dough, walnuts, sugar, butter, syrup', 'Baking in Oven'),
('Wine-Infused Beef Stew', 'Beef, red wine, vegetables, spices', 'Slow Cooking'),
('Braised Lamb in Red Wine Sauce', 'Lamb, red wine, herbs, garlic', 'Braising'),
('Chicken Marsala', 'Chicken, Marsala wine, mushrooms, butter', 'Sautéing'),
('Pork Tenderloin with Port Wine Sauce', 'Pork tenderloin, port wine, shallots, thyme', 'Roasting'),
('Beef Bourguignon', 'Beef, red wine, onions, carrots, mushrooms', 'Slow Cooking'),
('Baklava', 'Phyllo dough, walnuts, sugar, butter, syrup', 'Baking in Oven'),
('Rice Pudding', 'Rice, milk, sugar, vanilla', 'Baking in Oven'),
('Kazandibi', 'Milk, sugar, rice flour, butter', 'Cooking on Stove by Stirring'),
('Revani', 'Flour, sugar, eggs, semolina', 'Baking in Oven'),
('Kadaif', 'Kadaif dough, walnuts, sugar, butter, syrup', 'Baking in Oven'),
('Whole Wheat Bread', 'Whole wheat flour, water, yeast, salt', 'Baking in Oven'),
('Rye Bread', 'Rye flour, water, yeast, salt', 'Baking in Oven'),
('Bran Bread', 'Bran flour, water, yeast, salt', 'Baking in Oven'),
('Ciabatta', 'White flour, water, yeast, salt', 'Baking in Oven'),
('Olive Bread', 'White flour, water, yeast, salt, green olives', 'Baking in Oven'),
('Seasonal Salad', 'Mixed seasonal greens, tomatoes, cucumber, carrot, balsamic dressing', ''),
('Greek Salad', 'Lettuce, feta cheese, black olives, tomatoes, cucumber, olive oil', ''),
('Walnut Arugula Salad', 'Arugula, walnuts, parmesan cheese, olive oil, lemon juice', ''),
('Tuna Chickpea Salad', 'Tuna, chickpeas, lettuce, cherry tomatoes, balsamic dressing', ''),
('Feta Watermelon Salad', 'Watermelon, feta cheese, fresh mint, balsamic dressing', ''),
('Tzatziki Salad', 'Yogurt, cucumber, fresh mint, garlic', ''),
('Blue Cheese Arugula Salad', 'Blue cheese, arugula, walnuts, balsamic dressing', ''),
('Spinach Orange Salad', 'Spinach, orange slices, feta cheese, pomegranate sauce', ''),
('Mojito', 'White rum, lime, mint, soda water, sugar', 'On the Rocks'),
('Piña Colada', 'Coconut cream, pineapple juice, white rum', 'Blended'),
('Margarita', 'Tequila, triple sec, lime juice, salt', 'Straight Up'),
('Martini', 'Gin, dry vermouth, lemon twist', 'Straight Up'),
('Old Fashioned', 'Bourbon, sugar cube, bitters, orange twist', 'On the Rocks'),
('Negroni', 'Gin, vermouth, Campari, orange twist', 'On the Rocks'),
('Whiskey Sour', 'Bourbon, lemon juice, simple syrup', 'On the Rocks'),
('Mint Lemonade', 'Lemon juice, mint leaves, sugar, water', 'On the Rocks'),
('Ayran', 'Yogurt, water, salt', 'On the Rocks'),
('Cola', 'Cola, ice', 'On the Rocks'),
('Fanta', 'Fanta, ice', 'On the Rocks'),
('Lemonade', 'Lemon juice, sugar, water', 'On the Rocks'),
('Water', 'Water, ice', 'On the Rocks'),
('Yayık Ayran', 'Yogurt, water, salt', 'On the Rocks');
INSERT INTO Foods (Name, Ingredients, CookingMethod)
VALUES 
('Grilled Chicken Skewers', 'Chicken meat, olive oil, spices', 'Grilling'),
('Vegetable Lamb Casserole', 'Lamb meat, vegetables, tomato sauce', 'Oven Casserole'),
('Fish Pan', 'Sea bass, lemon, fresh herbs', 'Oven Baking'),
('Cauliflower Patties', 'Cauliflower, bulgur, onion, spices', 'Boiling, Frying'),
('Lentil Patties', 'Red lentils, bulgur, onion, spices', 'Boiling'),
('Chicken Chickpea Dish', 'Chicken meat, chickpeas, onion, garlic, spices', 'Boiling in Pot'),
('Grilled Meatballs', 'Beef minced meat, spices, onion', 'Grilling'),
('Vegetable Baked Potato', 'Potatoes, vegetables, cheddar cheese', 'Baking in Oven'),
('Olive Oil Zucchini Dolma', 'Zucchini, rice, onion, olive oil', 'Baking in Oven'),
('Chicken Baked Potato', 'Chicken, potatoes, corn, peas', 'Baking in Oven'),
('Spinach Pie', 'Spinach, phyllo dough, feta cheese', 'Baking in Oven'),
('Vegetable Stew', 'Vegetables, meat broth, spices', 'Boiling in Pot'),
('Sultans Delight', 'Lamb meat, eggplant, bechamel sauce', 'Baking in Oven'),
('Lamb Tandoori', 'Lamb meat, spices, yogurt', 'Baking in Oven'),
('Sautéed Mushrooms', 'Mushrooms, onion, olive oil', 'Sautéing'),
('Quinoa Salad', 'Quinoa, vegetables, olive oil', 'Mixing'),
('Lentil Vegan Meatballs', 'Red lentils, vegetables, spices', 'Frying'),
('Baked Vegetables', 'Broccoli, carrot, zucchini, olive oil', 'Baking in Oven'),
('Chickpea Vegan Curry', 'Chickpeas, vegetables, coconut milk', 'Sautéing'),
('Vegan Pizza', 'Pizza dough, tomato sauce, vegetables', 'Baking in Oven'),
('Seasonal Vegetarian Risotto', 'Arborio rice, vegetables, parmesan cheese', 'Mixing'),
('Spinach and Cheese Pastry', 'Spinach, feta cheese, phyllo dough', 'Baking in Oven'),
('Baked Potato', 'Potatoes, cheddar cheese, butter', 'Baking in Oven'),
('Vegetarian Noodle Stir-Fry', 'Noodles, vegetables, soy sauce', 'Sautéing'),
('Olive Oil Grape Leaves', 'Grape leaves filling, olive oil', 'Baking in Oven'),
('Wine-Infused Beef Stew', 'Beef, red wine, vegetables, spices', 'Slow Cooking'),
('Braised Lamb in Red Wine Sauce', 'Lamb, red wine, herbs, garlic', 'Braising'),
('Chicken Marsala', 'Chicken, Marsala wine, mushrooms, butter', 'Sautéing'),
('Pork Tenderloin with Port Wine Sauce', 'Pork tenderloin, port wine, shallots, thyme', 'Roasting'),
('Beef Bourguignon', 'Beef, red wine, onions, carrots, mushrooms', 'Slow Cooking'),
('Lentil Soup', 'Red lentils, onion, carrot', 'Boiling'),
('Tarhana Soup', 'Tarhana, yogurt, fresh herbs', 'Boiling'),
('Tomato Soup', 'Tomatoes, onion, fresh herbs', 'Boiling'),
('Head and Trotter Soup', 'Lamb head, chickpeas, spices', 'Boiling'),
('Ezo Gelin Soup', 'Red lentils, bulgur, onion, tomato paste', 'Boiling'),
('Yogurt Yayla Soup', 'Yogurt, flour, butter, mint', 'Boiling'),
('Vegetable Soup', 'Vegetables, meat broth, spices', 'Boiling'),
('Zucchini Soup', 'Zucchini, onion, milk', 'Boiling'),
('Vermicelli Soup', 'Vermicelli, chicken broth, spices', 'Boiling'),
('Bone Broth Soup', 'Bone broth, vegetables, spices', 'Boiling'),
('Chicken Soup', 'Chicken broth, vermicelli, fresh herbs', 'Boiling'),
('Bean Soup', 'Dry beans, onion, tomatoes', 'Boiling'),
('Mushroom Soup', 'Mushrooms, onion, cream', 'Boiling, Blending Smooth'),
('Lamb Meat Soup', 'Lamb meat, vegetables, spices', 'Boiling'),
('Zucchini Cartilage Soup', 'Zucchini, cartilage, chicken broth', 'Boiling'),
('Baklava', 'Phyllo dough, walnuts, sugar, butter, syrup', 'Baking in Oven'),
('Rice Pudding', 'Rice, milk, sugar, vanilla', 'Baking in Oven'),
('Kazandibi', 'Milk, sugar, rice flour, butter', 'Cooking on Stove by Stirring'),
('Revani', 'Flour, sugar, eggs, semolina', 'Baking in Oven'),
('Kadaif', 'Kadaif dough, walnuts, sugar, butter, syrup', 'Baking in Oven'),
('Wine-Infused Beef Stew', 'Beef, red wine, vegetables, spices', 'Slow Cooking'),
('Braised Lamb in Red Wine Sauce', 'Lamb, red wine, herbs, garlic', 'Braising'),
('Chicken Marsala', 'Chicken, Marsala wine, mushrooms, butter', 'Sautéing'),
('Pork Tenderloin with Port Wine Sauce', 'Pork tenderloin, port wine, shallots, thyme', 'Roasting'),
('Beef Bourguignon', 'Beef, red wine, onions, carrots, mushrooms', 'Slow Cooking'),
('Baklava', 'Phyllo dough, walnuts, sugar, butter, syrup', 'Baking in Oven'),
('Rice Pudding', 'Rice, milk, sugar, vanilla', 'Baking in Oven'),
('Kazandibi', 'Milk, sugar, rice flour, butter', 'Cooking on Stove by Stirring'),
('Revani', 'Flour, sugar, eggs, semolina', 'Baking in Oven'),
('Kadaif', 'Kadaif dough, walnuts, sugar, butter, syrup', 'Baking in Oven'),
('Whole Wheat Bread', 'Whole wheat flour, water, yeast, salt', 'Baking in Oven'),
('Rye Bread', 'Rye flour, water, yeast, salt', 'Baking in Oven'),
('Bran Bread', 'Bran flour, water, yeast, salt', 'Baking in Oven'),
('Ciabatta', 'White flour, water, yeast, salt', 'Baking in Oven'),
('Olive Bread', 'White flour, water, yeast, salt, green olives', 'Baking in Oven'),
('Seasonal Salad', 'Mixed seasonal greens, tomatoes, cucumber, carrot, balsamic dressing', ''),
('Greek Salad', 'Lettuce, feta cheese, black olives, tomatoes, cucumber, olive oil', ''),
('Walnut Arugula Salad', 'Arugula, walnuts, parmesan cheese, olive oil, lemon juice', ''),
('Tuna Chickpea Salad', 'Tuna, chickpeas, lettuce, cherry tomatoes, balsamic dressing', ''),
('Feta Watermelon Salad', 'Watermelon, feta cheese, fresh mint, balsamic dressing', ''),
('Tzatziki Salad', 'Yogurt, cucumber, fresh mint, garlic', ''),
('Blue Cheese Arugula Salad', 'Blue cheese, arugula, walnuts, balsamic dressing', ''),
('Spinach Orange Salad', 'Spinach, orange slices, feta cheese, pomegranate sauce', '');


INSERT INTO MainDishes (Name, Ingredients, CookingMethod)
VALUES 
('Grilled Chicken Skewers', 'Chicken meat, olive oil, spices', 'Grilling'),
('Vegetable Lamb Casserole', 'Lamb meat, vegetables, tomato sauce', 'Oven Casserole'),
('Fish Pan', 'Sea bass, lemon, fresh herbs', 'Oven Baking'),
('Cauliflower Patties', 'Cauliflower, bulgur, onion, spices', 'Boiling, Frying'),
('Lentil Patties', 'Red lentils, bulgur, onion, spices', 'Boiling'),
('Chicken Chickpea Dish', 'Chicken meat, chickpeas, onion, garlic, spices', 'Boiling in Pot'),
('Grilled Meatballs', 'Beef minced meat, spices, onion', 'Grilling'),
('Vegetable Baked Potato', 'Potatoes, vegetables, cheddar cheese', 'Baking in Oven'),
('Olive Oil Zucchini Dolma', 'Zucchini, rice, onion, olive oil', 'Baking in Oven'),
('Chicken Baked Potato', 'Chicken, potatoes, corn, peas', 'Baking in Oven'),
('Spinach Pie', 'Spinach, phyllo dough, feta cheese', 'Baking in Oven'),
('Vegetable Stew', 'Vegetables, meat broth, spices', 'Boiling in Pot'),
('Sultans Delight', 'Lamb meat, eggplant, bechamel sauce', 'Baking in Oven'),
('Lamb Tandoori', 'Lamb meat, spices, yogurt', 'Baking in Oven'),
('Sautéed Mushrooms', 'Mushrooms, onion, olive oil', 'Sautéing');

INSERT INTO VeganDishes (Name, Ingredients, CookingMethod)
VALUES 
('Quinoa Salad', 'Quinoa, vegetables, olive oil', 'Mixing'),
('Lentil Vegan Meatballs', 'Red lentils, vegetables, spices', 'Frying'),
('Baked Vegetables', 'Broccoli, carrot, zucchini, olive oil', 'Baking in Oven'),
('Chickpea Vegan Curry', 'Chickpeas, vegetables, coconut milk', 'Sautéing'),
('Vegan Pizza', 'Pizza dough, tomato sauce, vegetables', 'Baking in Oven');

INSERT INTO VegetarianDishes (Name, Ingredients, CookingMethod)
VALUES 
('Seasonal Vegetarian Risotto', 'Arborio rice, vegetables, parmesan cheese', 'Mixing'),
('Spinach and Cheese Pastry', 'Spinach, feta cheese, phyllo dough', 'Baking in Oven'),
('Baked Potato', 'Potatoes, cheddar cheese, butter', 'Baking in Oven'),
('Vegetarian Noodle Stir-Fry', 'Noodles, vegetables, soy sauce', 'Sautéing'),
('Olive Oil Grape Leaves', 'Grape leaves filling, olive oil', 'Baking in Oven');

INSERT INTO NonHalalDishes (Name, Ingredients, CookingMethod)
VALUES 
('Wine-Infused Beef Stew', 'Beef, red wine, vegetables, spices', 'Slow Cooking'),
('Braised Lamb in Red Wine Sauce', 'Lamb, red wine, herbs, garlic', 'Braising'),
('Chicken Marsala', 'Chicken, Marsala wine, mushrooms, butter', 'Sautéing'),
('Pork Tenderloin with Port Wine Sauce', 'Pork tenderloin, port wine, shallots, thyme', 'Roasting'),
('Beef Bourguignon', 'Beef, red wine, onions, carrots, mushrooms', 'Slow Cooking');

INSERT INTO Soups (Name, Ingredients, CookingMethod)
VALUES 
('Lentil Soup', 'Red lentils, onion, carrot', 'Boiling'),
('Tarhana Soup', 'Tarhana, yogurt, fresh herbs', 'Boiling'),
('Tomato Soup', 'Tomatoes, onion, fresh herbs', 'Boiling'),
('Head and Trotter Soup', 'Lamb head, chickpeas, spices', 'Boiling'),
('Ezo Gelin Soup', 'Red lentils, bulgur, onion, tomato paste', 'Boiling'),
('Yogurt Yayla Soup', 'Yogurt, flour, butter, mint', 'Boiling'),
('Vegetable Soup', 'Vegetables, meat broth, spices', 'Boiling'),
('Zucchini Soup', 'Zucchini, onion, milk', 'Boiling'),
('Vermicelli Soup', 'Vermicelli, chicken broth, spices', 'Boiling'),
('Bone Broth Soup', 'Bone broth, vegetables, spices', 'Boiling'),
('Chicken Soup', 'Chicken broth, vermicelli, fresh herbs', 'Boiling'),
('Bean Soup', 'Dry beans, onion, tomatoes', 'Boiling'),
('Mushroom Soup', 'Mushrooms, onion, cream', 'Boiling, Blending Smooth'),
('Lamb Meat Soup', 'Lamb meat, vegetables, spices', 'Boiling'),
('Zucchini Cartilage Soup', 'Zucchini, cartilage, chicken broth', 'Boiling');

INSERT INTO Desserts (Name, Ingredients, CookingMethod)
VALUES 
('Baklava', 'Phyllo dough, walnuts, sugar, butter, syrup', 'Baking in Oven'),
('Rice Pudding', 'Rice, milk, sugar, vanilla', 'Baking in Oven'),
('Kazandibi', 'Milk, sugar, rice flour, butter', 'Cooking on Stove by Stirring'),
('Revani', 'Flour, sugar, eggs, semolina', 'Baking in Oven'),
('Kadaif', 'Kadaif dough, walnuts, sugar, butter, syrup', 'Baking in Oven');

INSERT INTO Breads (Name, Ingredients, CookingMethod)
VALUES 
('Whole Wheat Bread', 'Whole wheat flour, water, yeast, salt', 'Baking in Oven'),
('Rye Bread', 'Rye flour, water, yeast, salt', 'Baking in Oven'),
('Bran Bread', 'Bran flour, water, yeast, salt', 'Baking in Oven'),
('Ciabatta', 'White flour, water, yeast, salt', 'Baking in Oven'),
('Olive Bread', 'White flour, water, yeast, salt, green olives', 'Baking in Oven');

INSERT INTO Salads (Name, Ingredients, CookingMethod)
VALUES 
('Seasonal Salad', 'Mixed seasonal greens, tomatoes, cucumber, carrot, balsamic dressing', ''),
('Greek Salad', 'Lettuce, feta cheese, black olives, tomatoes, cucumber, olive oil', ''),
('Walnut Arugula Salad', 'Arugula, walnuts, parmesan cheese, olive oil, lemon juice', ''),
('Tuna Chickpea Salad', 'Tuna, chickpeas, lettuce, cherry tomatoes, balsamic dressing', ''),
('Feta Watermelon Salad', 'Watermelon, feta cheese, fresh mint, balsamic dressing', ''),
('Tzatziki Salad', 'Yogurt, cucumber, fresh mint, garlic', ''),
('Blue Cheese Arugula Salad', 'Blue cheese, arugula, walnuts, balsamic dressing', ''),
('Spinach Orange Salad', 'Spinach, orange slices, feta cheese, pomegranate sauce', '');

INSERT INTO BEVERAGES (Name, Ingredients, ServingStyle) VALUES
('Mojito', 'White rum, lime, mint, soda water, sugar', 'On the Rocks'),
('Piña Colada', 'Coconut cream, pineapple juice, white rum', 'Blended'),
('Margarita', 'Tequila, triple sec, lime juice, salt', 'Straight Up'),
('Martini', 'Gin, dry vermouth, lemon twist', 'Straight Up'),
('Old Fashioned', 'Bourbon, sugar cube, bitters, orange twist', 'On the Rocks'),
('Negroni', 'Gin, vermouth, Campari, orange twist', 'On the Rocks'),
('Whiskey Sour', 'Bourbon, lemon juice, simple syrup', 'On the Rocks'),
('Mint Lemonade', 'Lemon juice, mint leaves, sugar, water', 'On the Rocks'),
('Ayran', 'Yogurt, water, salt', 'On the Rocks'),
('Cola', 'Cola, ice', 'On the Rocks'),
('Fanta', 'Fanta, ice', 'On the Rocks'),
('Lemonade', 'Lemon juice, sugar, water', 'On the Rocks'),
('Water', 'Water, ice', 'On the Rocks'),
('Yayık Ayran', 'Yogurt, water, salt', 'On the Rocks');


INSERT INTO AlcoholicBeverages (Name, Ingredients, ServingStyle) VALUES 
('Mojito', 'White rum, lime, mint, soda water, sugar', 'On the Rocks'),
('Piña Colada', 'Coconut cream, pineapple juice, white rum', 'Blended'),
('Margarita', 'Tequila, triple sec, lime juice, salt', 'Straight Up'),
('Martini', 'Gin, dry vermouth, lemon twist', 'Straight Up'),
('Old Fashioned', 'Bourbon, sugar cube, bitters, orange twist', 'On the Rocks'),
('Negroni', 'Gin, vermouth, Campari, orange twist', 'On the Rocks'),
('Whiskey Sour', 'Bourbon, lemon juice, simple syrup', 'On the Rocks');


INSERT INTO NonAlcoholicBeverages (Name, Ingredients, ServingStyle) VALUES
('Mint Lemonade', 'Lemon juice, mint leaves, sugar, water', 'On the Rocks'),
('Ayran', 'Yogurt, water, salt', 'On the Rocks'),
('Cola', 'Cola, ice', 'On the Rocks'),
('Fanta', 'Fanta, ice', 'On the Rocks'),
('Lemonade', 'Lemon juice, sugar, water', 'On the Rocks'),
('Water', 'Water, ice', 'On the Rocks'),
('Yayık Ayran', 'Yogurt, water, salt', 'On the Rocks');


DROP VIEW IF EXISTS New_RestaurantMenu;

CREATE VIEW New_RestaurantMenu AS
SELECT ID, Name, Ingredients, CookingMethod, NULL AS ServingStyle FROM AllOfTheRestaurantMenu 
UNION 
SELECT ID, Name, Ingredients, CookingMethod, NULL FROM Foods 
UNION 
SELECT ID, Name, Ingredients, CookingMethod, NULL FROM MainDishes 
UNION 
SELECT ID, Name, Ingredients, CookingMethod, NULL FROM VegetarianDishes 
UNION 
SELECT ID, Name, Ingredients, CookingMethod, NULL FROM VeganDishes 
UNION 
SELECT ID, Name, Ingredients, CookingMethod, NULL FROM NonHalalDishes 
UNION 
SELECT ID, Name, Ingredients, CookingMethod, NULL FROM Soups 
UNION 
SELECT ID, Name, Ingredients, CookingMethod, NULL FROM Desserts 
UNION 
SELECT ID, Name, Ingredients, CookingMethod, NULL FROM Breads 
UNION 
SELECT ID, Name, Ingredients, NULL, NULL FROM Salads 
UNION 
SELECT ID, Name, Ingredients, NULL, ServingStyle FROM BEVERAGES 
UNION 
SELECT ID, Name, Ingredients, NULL, ServingStyle FROM AlcoholicBeverages 
UNION 
SELECT ID, Name, Ingredients, NULL, ServingStyle FROM NonAlcoholicBeverages;

    
UPDATE AllOfTheRestaurantMenu
SET Price = 14.99
WHERE Name IN ('Mojito', 'Piña Colada', 'Margarita', 'Martini', 'Old Fashioned', 'Negroni', 'Whiskey Sour', 'Mint Lemonade', 'Ayran', 'Cola', 'Fanta', 'Lemonade', 'Water', 'Yayık Ayran');

UPDATE AllOfTheRestaurantMenu
SET Price = 24.99
WHERE Name IN ('Seasonal Salad', 'Greek Salad', 'Walnut Arugula Salad', 'Tuna Chickpea Salad', 'Feta Watermelon Salad', 'Tzatziki Salad', 'Blue Cheese Arugula Salad', 'Spinach Orange Salad');

UPDATE AllOfTheRestaurantMenu
SET Price = 8.99
WHERE Name IN ('Whole Wheat Bread', 'Rye Bread', 'Bran Bread', 'Ciabatta', 'Olive Bread');

UPDATE AllOfTheRestaurantMenu
SET Price = 34.99
WHERE Name IN ('Baklava', 'Rice Pudding', 'Kazandibi', 'Revani', 'Kadaif');

UPDATE AllOfTheRestaurantMenu
SET Price = 48.99
WHERE Name IN (
  'Lentil Soup', 'Tarhana Soup', 'Tomato Soup', 'Head and Trotter Soup',
  'Ezo Gelin Soup', 'Yogurt Yayla Soup', 'Vegetable Soup', 'Zucchini Soup',
  'Vermicelli Soup', 'Bone Broth Soup', 'Chicken Soup', 'Bean Soup',
  'Mushroom Soup', 'Lamb Meat Soup', 'Zucchini Cartilage Soup'
);

UPDATE AllOfTheRestaurantMenu
SET Price = 78.99
WHERE Name IN (
  'Wine-Infused Beef Stew', 'Braised Lamb in Red Wine Sauce', 'Chicken Marsala',
  'Pork Tenderloin with Port Wine Sauce', 'Beef Bourguignon'
);

UPDATE AllOfTheRestaurantMenu
SET Price = 119.99
WHERE Name IN (
  'Seasonal Vegetarian Risotto', 'Spinach and Cheese Pastry', 'Baked Potato',
  'Vegetarian Noodle Stir-Fry', 'Olive Oil Grape Leaves'
);

UPDATE AllOfTheRestaurantMenu
SET Price = 129.99
WHERE Name IN (
  'Quinoa Salad', 'Lentil Vegan Meatballs', 'Baked Vegetables',
  'Chickpea Vegan Curry', 'Vegan Pizza'
);

UPDATE AllOfTheRestaurantMenu
SET Price = 99.99
WHERE Name IN (
  'Grilled Chicken Skewers', 'Vegetable Lamb Casserole', 'Fish Pan',
  'Cauliflower Patties', 'Lentil Patties', 'Chicken Chickpea Dish',
  'Grilled Meatballs', 'Vegetable Baked Potato', 'Olive Oil Zucchini Dolma',
  'Chicken Baked Potato', 'Spinach Pie', 'Vegetable Stew',
  'Sultans Delight', 'Lamb Tandoori', 'Sautéed Mushrooms'
);































