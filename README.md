import { useState, useEffect } from "react";

export default function CardEditor() {
  const [title, setTitle] = useState("");
  const [image, setImage] = useState(null);

  useEffect(() => {
    return () => {
      if (image) URL.revokeObjectURL(image);
    };
  }, [image]);

  const handleImageUpload = (e) => {
    const file = e.target.files[0];
    if (file) {
      setImage(URL.createObjectURL(file));
    }
  };export default function TarotCardScreen() {
  return (
    <div className="min-h-screen bg-black text-white">
      
      {/* Header */}
      <div className="flex justify-between items-center p-4 text-yellow-400">
        <span>← Today’s Tarot Card</span>
        <span>⤴</span>
      </div>

      {/* Card Image */}
      <div className="flex justify-center mt-4">
        <img
          src="/queen-of-wands.jpg"
          alt="Queen of Wands"
          className="w-48 rounded-xl shadow-lg"
        />
      </div>

      {/* Info Panel */}
      <div className="m-4 p-4 bg-black/70 rounded-xl">
        <h2 className="text-yellow-400 text-xl mb-2">
          Queen of Wands
        </h2>

        <p className="text-sm leading-relaxed text-gray-200">
          The Queen of Wands represents confidence, passion, and leadership...
        </p>
      </div>

      {/* Bottom Nav */}
      <div className="fixed bottom-0 w-full flex justify-around p-3 bg-black border-t border-gray-800 text-sm">
        <span>Readings</span>
        <span>Meanings</span>
        <span>Quiz</span>
        <span>Courses</span>
        <span>More</span>
      </div>
    </div>
  );
}qimport { useState } from "react";

export default function CardEditor() {
  const [title, setTitle] = useState("");
  const [image, setImage] = useState(null);

  const handleImageUpload = (e) => {
    setImage(URL.createObjectURL(e.target.files[0]));
  };

  return (
    <div className="p-4">
      <input
        placeholder="Card Title"
        value={title}
        onChange={(e) => setTitle(e.target.value)}
        className="border p-2 mb-2"
      />

      <input type="file" onChange={handleImageUpload} />

      <div className="mt-4 border p-4 w-64">
        {image && <img src={image} alt="card" />}
        <h2 className="text-center font-bold">{title}</h2>
      </div>
    </div>
  );
}export default function TarotCardScreen() {
  return (
    <div className="min-h-screen bg-black text-white">
      
      {/* Header */}
      <div className="flex justify-between items-center p-4 text-yellow-400">
        <span>← Today’s Tarot Card</span>
        <span>⤴</span>
      </div>

      {/* Card Image */}
      <div className="flex justify-center mt-4">
        <img
          src="/queen-of-wands.jpg"
          alt="Queen of Wands"
          className="w-48 rounded-xl shadow-lg"
        />
      </div>

      {/* Info Panel */}
      <div className="m-4 p-4 bg-black/70 rounded-xl">
        <h2 className="text-yellow-400 text-xl mb-2">
          Queen of Wands
        </h2>

        <p className="text-sm leading-relaxed text-gray-200">
          The Queen of Wands represents confidence, passion, and leadership...
        </p>
      </div>

      {/* Bottom Nav */}
      <div className="fixed bottom-0 w-full flex justify-around p-3 bg-black border-t border-gray-800 text-sm">
        <span>Readings</span>
        <span>Meanings</span>
        <span>Quiz</span>
        <span>Courses</span>
        <span>More</span>
      </div>
    </div>
  );
} Spell8
My tarot app
