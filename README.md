import { MessageCircle } from 'lucide-react';
import { useState } from 'react';

export default function NursingCollegeWebsite() {
  const [formSubmitted, setFormSubmitted] = useState(false);

  const handleSubmit = (e) => {
    e.preventDefault();

    const formData = new FormData(e.target);

    const student = {
      name: formData.get('name') || '',
      mobile: formData.get('mobile') || '',
      email: formData.get('email') || '',
      course: formData.get('course') || '',
      address: formData.get('address') || '',
    };

    console.log('Admission Form Data:', student);

    setFormSubmitted(true);
    e.target.reset();

    setTimeout(() => {
      setFormSubmitted(false);
    }, 3000);
  };

  return (
    <div className="min-h-screen bg-gray-50 text-gray-800">
      {/* Hero Section */}
      <section className="relative bg-gradient-to-r from-pink-600 to-red-500 text-white py-20 px-6 overflow-hidden">
        <div className="max-w-7xl mx-auto grid md:grid-cols-2 gap-10 items-center">
          <div className="absolute top-6 left-6 bg-white p-3 rounded-2xl shadow-xl">
            <img
              src="https://upload.wikimedia.org/wikipedia/commons/a/ab/Logo_TV_2015.png"
              alt="College Logo"
              className="w-20 h-20 object-contain"
            />
          </div>

          <div>
            <h1 className="text-5xl font-bold leading-tight mb-6">
              Rajarshi Shahu Maharaj College of Nursing Kohmara
            </h1>

            <p className="text-lg mb-6">
              Empowering Future Healthcare Professionals with Quality Nursing Education.
            </p>

            <div className="flex gap-4 flex-wrap">
              <button
                type="button"
                className="bg-white text-pink-600 px-6 py-3 rounded-2xl shadow-lg font-semibold hover:scale-105 transition"
              >
                Apply Now
              </button>

              <button
                type="button"
                className="border border-white px-6 py-3 rounded-2xl hover:bg-white hover:text-pink-600 transition"
              >
                Contact Us
              </button>
            </div>
          </div>

          <div>
            <img
              src="https://images.unsplash.com/photo-1584515933487-779824d29309?q=80&w=1200&auto=format&fit=crop"
              alt="Nursing Students"
              className="rounded-3xl shadow-2xl w-full"
            />
          </div>
        </div>
      </section>

      {/* About Section */}
      <section className="py-16 px-6 max-w-7xl mx-auto">
        <div className="grid md:grid-cols-2 gap-10 items-center">
          <img
            src="https://images.unsplash.com/photo-1516549655169-df83a0774514?q=80&w=1200&auto=format&fit=crop"
            alt="College Campus"
            className="rounded-3xl shadow-lg w-full"
          />

          <div>
            <h2 className="text-4xl font-bold mb-4 text-pink-600">
              About Our College
            </h2>

            <p className="text-lg leading-relaxed mb-4">
              Our Nursing College is dedicated to providing excellent education,
              practical training, and healthcare knowledge to students.
            </p>

            <p className="text-lg leading-relaxed">
              Modern labs, experienced faculty, hospital training, and a supportive
              campus environment help students become successful healthcare professionals.
            </p>
          </div>
        </div>
      </section>

      {/* Courses Section */}
      <section className="bg-white py-16 px-6">
        <div className="max-w-7xl mx-auto text-center">
          <h2 className="text-4xl font-bold text-pink-600 mb-12">
            Our Courses
          </h2>

          <div className="flex justify-center">
            <div className="bg-gray-100 p-8 rounded-3xl shadow-md hover:shadow-2xl transition max-w-md w-full">
              <h3 className="text-2xl font-bold mb-4 text-pink-600">
                GNM Nursing
              </h3>

              <p>
                Comprehensive training in patient care and nursing practices.
              </p>
            </div>
          </div>
        </div>
      </section>

      {/* Gallery Section */}
      <section className="bg-gray-100 py-16 px-6">
        <div className="max-w-7xl mx-auto">
          <h2 className="text-4xl font-bold text-center text-pink-600 mb-12">
            College Gallery
          </h2>

          <div className="grid md:grid-cols-3 gap-6">
            {[
              'https://images.unsplash.com/photo-1527613426441-4da17471b66d?q=80&w=1200&auto=format&fit=crop',
              'https://images.unsplash.com/photo-1588776814546-1ffcf47267a5?q=80&w=1200&auto=format&fit=crop',
              'https://images.unsplash.com/photo-1576091160550-2173dba999ef?q=80&w=1200&auto=format&fit=crop',
            ].map((img, index) => (
              <img
                key={index}
                src={img}
                alt="College"
                className="rounded-3xl shadow-xl h-72 w-full object-cover hover:scale-105 transition duration-300"
              />
            ))}
          </div>
        </div>
      </section>

      {/* Online Admission Form */}
      <section className="bg-white py-16 px-6">
        <div className="max-w-4xl mx-auto bg-pink-50 rounded-3xl shadow-2xl p-10">
          <h2 className="text-4xl font-bold text-center text-pink-600 mb-10">
            Online Admission Form
          </h2>

          {formSubmitted && (
            <div className="mb-6 bg-green-100 text-green-700 p-4 rounded-2xl text-center font-semibold">
              Admission Form Submitted Successfully
            </div>
          )}

          <form onSubmit={handleSubmit} className="grid md:grid-cols-2 gap-6">
            <input
              name="name"
              type="text"
              placeholder="Student Full Name"
              className="p-4 rounded-2xl border"
              required
            />

            <input
              name="mobile"
              type="text"
              placeholder="Mobile Number"
              className="p-4 rounded-2xl border"
              required
            />

            <input
              name="email"
              type="email"
              placeholder="Email Address"
              className="p-4 rounded-2xl border"
              required
            />

            <select
              name="course"
              className="p-4 rounded-2xl border"
              required
            >
              <option value="">Select Course</option>
              <option value="GNM Nursing">GNM Nursing</option>
            </select>

            <textarea
              name="address"
              placeholder="Address"
              rows={4}
              className="md:col-span-2 p-4 rounded-2xl border"
              required
            />

            <button
              type="submit"
              className="md:col-span-2 bg-pink-600 text-white py-4 rounded-2xl text-lg font-bold hover:bg-pink-700 transition"
            >
              Submit Admission Form
            </button>
          </form>
        </div>
      </section>

      {/* Facilities */}
      <section className="py-16 px-6 max-w-7xl mx-auto">
        <h2 className="text-4xl font-bold text-center text-pink-600 mb-12">
          Campus Facilities
        </h2>

        <div className="grid md:grid-cols-4 gap-6">
          {[
            'Modern Labs',
            'Library',
            'Hostel Facility',
            'Hospital Training',
          ].map((item, index) => (
            <div
              key={index}
              className="bg-pink-50 border border-pink-100 rounded-2xl p-6 text-center shadow"
            >
              <h3 className="font-bold text-xl text-pink-600">{item}</h3>
            </div>
          ))}
        </div>
      </section>

      {/* Admission Banner */}
      <section className="bg-gradient-to-r from-red-500 to-pink-600 text-white py-16 px-6 text-center">
        <h2 className="text-4xl font-bold mb-4">
          Admissions Open 2025-26
        </h2>

        <p className="text-lg mb-6">
          Start your career in healthcare with professional nursing education.
        </p>

        <button
          type="button"
          className="bg-white text-pink-600 px-8 py-4 rounded-2xl font-bold shadow-lg hover:scale-105 transition"
        >
          Apply for Admission
        </button>
      </section>

      {/* Contact Section */}
      <section className="py-16 px-6 bg-white">
        <div className="max-w-5xl mx-auto grid md:grid-cols-2 gap-10">
          <div>
            <h2 className="text-4xl font-bold text-pink-600 mb-6">
              Contact Us
            </h2>

            <p className="mb-3 text-lg">
              📍 Kohmara, Sadak Arjuni, Gondia, 441807
            </p>

            <p className="mb-3 text-lg">📞 +91 8999187955</p>

            <p className="mb-3 text-lg">
              ✉️ rsmcollegeofnursing@gmail.com
            </p>
          </div>

          <form className="bg-gray-100 p-8 rounded-3xl shadow-lg space-y-4">
            <input
              type="text"
              placeholder="Your Name"
              className="w-full p-3 rounded-xl border"
            />

            <input
              type="email"
              placeholder="Your Email"
              className="w-full p-3 rounded-xl border"
            />

            <textarea
              placeholder="Your Message"
              rows={4}
              className="w-full p-3 rounded-xl border"
            />

            <button
              type="button"
              className="bg-pink-600 text-white px-6 py-3 rounded-2xl hover:bg-pink-700 transition"
            >
              Send Message
            </button>
          </form>
        </div>
      </section>
      {/* Footer */}
      <footer className="bg-gray-900 text-white py-8 text-center">
        <p className="mb-4">
          © 2026 Rajarshi Shahu Maharaj College of Nursing | All Rights Reserved.
        </p>

        <div className="flex flex-wrap justify-center gap-6 text-sm md:text-base">
          <a href="#" className="hover:text-pink-400 transition">
            About Us
          </a>

          <a href="#" className="hover:text-pink-400 transition">
            Contact Us
          </a>

          <a href="#" className="hover:text-pink-400 transition">
            Privacy Policy
          </a>

          <a href="#" className="hover:text-pink-400 transition">
            Disclaimer
          </a>

          <a href="#" className="hover:text-pink-400 transition">
            Terms & Conditions
          </a>
        </div>
      </footer>

      {/* WhatsApp Button */}
      <a
        href="https://wa.me/918999187955"
        target="_blank"
        rel="noopener noreferrer"
        className="fixed bottom-6 right-6 bg-green-500 text-white p-4 rounded-full shadow-2xl hover:scale-110 transition z-50"
      >
        <MessageCircle size={32} />
      </a>
    </div>
  );
}
