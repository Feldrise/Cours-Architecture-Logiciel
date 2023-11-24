# Travaux Pratiques : Maîtriser les Techniques de Tests en JavaScript 🧪

Salut les futurs développeurs ! Aujourd'hui, on va plonger dans l'univers passionnant des tests en développement logiciel. On va apprendre ensemble à écrire des tests solides qui vont booster la qualité de vos projets JavaScript. Prêts ? C'est parti ! 🚀

## 📚 Comprendre les Tests Logiciels

### Pourquoi Tester ?
- Les tests assurent que votre code fait ce qu'il est supposé faire.
- Ils vous aident à identifier les bugs plus tôt, ce qui économise du temps et de l'argent.
- Un bon ensemble de tests rend votre code plus fiable et plus facile à maintenir.

### Types de Tests
1. **Tests Unitaires :** Ils testent des parties individuelles de votre code (comme les fonctions) isolément.
2. **Tests d'Intégration :** Ils vérifient comment différentes parties de votre application travaillent ensemble.
3. **Tests Fonctionnels :** Ils évaluent le comportement de votre application du point de vue de l'utilisateur final.

## 💻 Mise en Pratique avec JavaScript

### Configuration de l'Environnement
1. **Installer Jest :** C'est un framework de test populaire pour JavaScript.
   ```bash
   npm install --save-dev jest
   ```

### Écrire des Tests Unitaires
#### Exemple 1 : Tester une Fonction Simple
- **Fonction :** `add(a, b)` qui additionne deux nombres.
  ```javascript
  function add(a, b) {
    return a + b;
  }
  ```
- **Test :**
  ```javascript
  test('additionner 1 + 2 donne 3', () => {
    expect(add(1, 2)).toBe(3);
  });
  ```

#### Exemple 2 : Tester une Fonction avec Conditions
- **Fonction :** `greet(name)` qui renvoie des salutations personnalisées.
  ```javascript
  function greet(name) {
    return name ? `Bonjour, ${name}!` : 'Bonjour, invité!';
  }
  ```
- **Tests :**
  ```javascript
  test('saluer avec un nom', () => {
    expect(greet('Alice')).toBe('Bonjour, Alice!');
  });

  test('saluer sans nom', () => {
    expect(greet(null)).toBe('Bonjour, invité!');
  });
  ```

#### Exemple 3 : Tester une Fonction qui Lance une Exception
- **Fonction :** `divide(a, b)` qui divise `a` par `b`.
  ```javascript
  function divide(a, b) {
    if (b === 0) {
      throw new Error('Division par zéro!');
    }
    return a / b;
  }
  ```
- **Tests :**
  ```javascript
  test('diviser 6 par 3 donne 2', () => {
    expect(divide(6, 3)).toBe(2);
  });

  test('division par zéro lance une erreur', () => {
    expect(() => divide(6, 0)).toThrow('Division par zéro!');
  });
  ```

#### Exemple 4 : Tester des Cas de Bord
- **Fonction :** `isPrime(number)` qui vérifie si un nombre est premier.
  ```javascript
  function isPrime(number) {
    if (number <= 1) return false;
    if (number <= 3) return true;

    if (number % 2 === 0 || number % 3 === 0) return false;

    for (let i = 5; i * i <= number; i += 6) {
      if (number % i === 0 || number % (i + 2) === 0) return false;
    }

    return true;
  }
  ```
- **Tests :**
  ```javascript
  test('5 est un nombre premier', () => {
    expect(isPrime(5)).toBeTruthy();
  });

  test('4 n\'est pas un nombre premier', () => {
    expect(isPrime(4)).toBeFalsy();
  });

  test('0 et 1 ne sont pas des nombres premiers', () => {
    expect(isPrime(0)).toBeFalsy();
    expect(isPrime(1)).toBeFalsy();
  });

  test('2 est un nombre premier', () => {
    expect(isPrime(2)).toBeTruthy();
  });
  ```

Avec ces exemples, vous devriez être en mesure de commencer à écrire des tests unitaires efficaces pour vos fonctions JavaScript. N'oubliez pas que la pratique est essentielle pour maîtriser ces compétences. Bonne chance ! 🌟👨‍💻👩‍💻

### Tests d'Intégration
### Tests d'Intégration pour NextJS
#### 📋 Cahier des Charges
Imaginons que vous développiez une petite application e-commerce NextJS. Voici les fonctionnalités clés :

1. **Page d'Accueil :** Affiche les produits en vedette.
2. **Liste de Produits :** Affiche tous les produits disponibles.
3. **Détails du Produit :** Affiche les informations détaillées d'un produit spécifique.
4. **Panier d'Achat :** Permet aux utilisateurs d'ajouter et de supprimer des produits.
5. **Processus de Paiement :** Gère la saisie des informations de paiement et de livraison.

#### 🧪 Exemple de Test d'Intégration
Prenons la fonctionnalité "Panier d'Achat" pour notre exemple. Nous allons tester l'intégration entre la liste de produits et le panier d'achat.

**Scénario de Test :** Ajouter un produit depuis la liste de produits au panier d'achat et vérifier s'il apparaît correctement dans le panier.

1. **Préparation :**
   - Installez des outils de test comme Jest et React Testing Library.
   - Assurez-vous que votre environnement NextJS est configuré pour le test.

   ```bash
   npm install --save-dev jest @testing-library/react @testing-library/jest-dom
   ```

2. **Écriture du Test :**
   - Créez un test qui simule l'ajout d'un produit au panier depuis la liste de produits.

   ```javascript
   import { render, fireEvent, waitFor } from '@testing-library/react';
   import App from '../pages/index';
   import Cart from '../components/Cart';

   describe('Panier d\'Achat Integration', () => {
     it('permet à l\'utilisateur d\'ajouter un produit au panier', async () => {
       const { getByText, getByTestId } = render(<App />);
       
       // Simulez l'ajout d'un produit au panier
       fireEvent.click(getByText('Ajouter au Panier'));

       // Attendez que le panier soit mis à jour
       await waitFor(() => getByTestId('cart'));

       // Vérifiez si le produit est dans le panier
       const cart = render(<Cart />);
       expect(cart.getByText('Produit Ajouté')).toBeInTheDocument();
     });
   });
   ```

3. **Exécution et Analyse :**
   - Exécutez le test et analysez les résultats.
   - Si le test échoue, vérifiez les interactions entre les composants et corrigez les problèmes.

4. Essayez d'imaginer d'autres tests.

### Tests Fonctionnels
- **Exemple sur une application réelle**

### Bonnes Pratiques
- **Gardez vos tests à jour :** Comme votre code évolue, vos tests doivent évoluer avec lui.
- **Couverture de Test :** Visez une couverture de test élevée, mais n'oubliez pas que 100% de couverture ne signifie pas 0% de bugs.

## 🎯 Conclusion

Maintenant, c'est à vous de jouer ! Utilisez ce que vous avez appris pour écrire des tests pour vos propres projets. Rappelez-vous, des tests robustes sont la clé pour construire des applications fiables et maintenables. Amusez-vous bien et codez prudemment ! 👨‍💻👩‍💻🔧

---

Et voilà ! Vous avez maintenant toutes les clés en main pour devenir des pros du test en JavaScript. Si vous avez des questions, n'hésitez pas à les poser. Bonne chance ! 🌟