✨ Welcome to My GitHub! ✨







Building solutions that sparkle with innovation! 🌟

About Me

I'm [Your Name], a developer passionate about creating user-friendly web apps. My projects empower users, from shopkeepers to gamers, with modern tech and a touch of creativity.





Skills: JavaScript, Next.js, React, HTML, CSS



Mission: Code that simplifies lives and inspires joy

🔥 Key Projects

These are my key personal projects, showcasing my skills and passion:

DukaSmart





Description: A user-friendly informational website to empower local shopkeepers with digital tools for inventory management and sales tracking. A smart duka means a smart life!



Tech Stack: Next.js, Tailwind CSS



Link: DukaSmart



Code Snippet: Inventory management component

// components/Inventory.js
import { useState } from 'react';

export default function Inventory() {
  const [items, setItems] = useState([
    { id: 1, name: 'Rice', quantity: 50, price: 100 },
    { id: 2, name: 'Beans', quantity: 30, price: 80 },
  ]);

  const addItem = (newItem) => {
    setItems([...items, { id: items.length + 1, ...newItem }]);
  };

  return (
    <div className="p-4">
      <h2 className="text-2xl font-bold">Inventory Management</h2>
      <table className="w-full mt-4 border">
        <thead>
          <tr>
            <th className="border p-2">Item</th>
            <th className="border p-2">Quantity</th>
            <th className="border p-2">Price</th>
          </tr>
        </thead>
        <tbody>
          {items.map(item => (
            <tr key={item.id}>
              <td className="border p-2">{item.name}</td>
              <td className="border p-2">{item.quantity}</td>
              <td className="border p-2">{item.price}</td>
            </tr>
          ))}
        </tbody>
      </table>
      <button
        className="mt-4 bg-blue-500 text-white p-2 rounded"
        onClick={() => addItem({ name: 'New Item', quantity: 10, price: 50 })}
      >
        Add Item
      </button>
    </div>
  );
}

Detective Game





Description: A web-based multiplayer detective board game with customizable avatars and mini-games (word search, talk-it-out, DNA quiz, mystery events, food web building). Players roll dice to win.



Tech Stack: JavaScript, HTML, CSS



Link: GitHub Repo



Code Snippet: Dice roll and player movement

// scripts/game.js
class DetectiveGame {
  constructor() {
    this.players = [
      { id: 1, position: 0, points: 0, avatar: 'detective1.png' },
      { id: 2, position: 0, points: 0, avatar: 'detective2.png' },
    ];
    this.boardSize = 20;
  }

  rollDice() {
    return Math.floor(Math.random() * 6) + 1;
  }

  movePlayer(playerId) {
    const player = this.players.find(p => p.id === playerId);
    const roll = this.rollDice();
    player.position = (player.position + roll) % this.boardSize;
    console.log(`Player ${playerId} rolled a ${roll} and moved to position ${player.position}`);
    if (player.position === 10) {
      this.startMiniGame(player);
    }
  }

  startMiniGame(player) {
    const miniGames = ['word-search', 'talk-it-out', 'dna-quiz', 'mystery-events', 'food-web'];
    const game = miniGames[Math.floor(Math.random() * miniGames.length)];
    console.log(`Player ${player.id} starts ${game}!`);
    player.points += 1;
    if (player.points >= 5) console.log(`Player ${player.id} wins!`);
  }
}

const game = new DetectiveGame();
document.getElementById('roll-btn').addEventListener('click', () => game.movePlayer(1));

LushMuse





Description: A web app inspired by Lush, focusing on user account creation with clean UI, form validation, and localStorage-based registration.



Tech Stack: HTML, CSS, JavaScript, React



Link: GitHub Repo



Code Snippet: Signup form with validation

// components/SignupForm.js
import { useState } from 'react';

export default function SignupForm() {
  const [formData, setFormData] = useState({ email: '', password: '', phone: '' });
  const [errors, setErrors] = useState({});

  const validate = () => {
    const newErrors = {};
    if (!formData.email.match(/^[^\s@]+@[^\s@]+\.[^\s@]+$/)) newErrors.email = 'Invalid email';
    if (formData.password.length < 6) newErrors.password = 'Password must be at least 6 characters';
    if (!formData.phone.match(/^\d{10}$/)) newErrors.phone = 'Phone must be 10 digits';
    return newErrors;
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    const validationErrors = validate();
    if (Object.keys(validationErrors).length === 0) {
      localStorage.setItem('user', JSON.stringify(formData));
      alert('Signup successful!');
    } else {
      setErrors(validationErrors);
    }
  };

  return (
    <form onSubmit={handleSubmit} className="p-4 max-w-md mx-auto">
      <h2 className="text-2xl font-bold mb-4">Sign Up</h2>
      <div className="mb-4">
        <input
          type="email"
          placeholder="Email"
          value={formData.email}
          onChange={(e) => setFormData({ ...formData, email: e.target.value })}
          className="w-full p-2 border rounded"
        />
        {errors.email && <p className="text-red-500">{errors.email}</p>}
      </div>
      <div className="mb-4">
        <input
          type="password"
          placeholder="Password"
          value={formData.password}
          onChange={(e) => setFormData({ ...formData, password: e.target.value })}
          className="w-full p-2 border rounded"
        />
        {errors.password && <p className="text-red-500">{errors.password}</p>}
      </div>
      <div className="mb-4">
        <input
          type="tel"
          placeholder="Phone"
          value={formData.phone}
          onChange={(e) => setFormData({ ...formData, phone: e.target.value })}
          className="w-full p-2 border rounded"
        />
        {errors.phone && <p className="text-red-500">{errors.phone}</p>}
      </div>
      <button type="submit" className="bg-pink-500 text-white p-2 rounded w-full">
        Sign Up
      </button>
    </form>
  );
}

Connect

Let’s make the web shine! 🌐





📧 Email: your.email@example.com



🐦 X: @yourusername



Built with ✨ and 💖
