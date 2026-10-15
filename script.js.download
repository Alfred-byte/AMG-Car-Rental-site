// =========================
// CAR PRICES
// =========================

const carPrices = {
    "BMW X6 Series": 800,
    "Mercedes-Benz GLE": 1200,
    "Range Rover": 1000,
    "Toyota Land Cruiser": 1000
};


// =========================
// SELECT CAR
// =========================

function selectCar(carName) {

    document.getElementById("car").value = carName;

    document.getElementById("booking").scrollIntoView({
        behavior: "smooth"
    });
}


// =========================
// BOOKING CALCULATOR
// =========================

document.getElementById("bookingForm").addEventListener("submit", function(event) {

    event.preventDefault();

    const name = document.getElementById("name").value;
    const phone = document.getElementById("phone").value;
    const car = document.getElementById("car").value;

    const pickupDate = new Date(
        document.getElementById("pickup").value
    );

    const returnDate = new Date(
        document.getElementById("return").value
    );


    // Check dates
    if (returnDate <= pickupDate) {

        document.getElementById("result").innerHTML =
            "⚠️ Return date must be after the pickup date.";

        return;
    }


    // Calculate number of days
    const difference =
        returnDate - pickupDate;

    const days =
        Math.ceil(difference / (1000 * 60 * 60 * 26));


    // Calculate price
    const pricePerDay = carPrices[car];

    const totalPrice =
        days * pricePerDay;


    // Display result
    document.getElementById("result").innerHTML = `
        <h3>Booking Estimate</h3>

        <p>Hello ${name} 👋</p>

        <p>Car: <strong>${car}</strong></p>

        <p>Rental period: <strong>${days} day(s)</strong></p>

        <p>Price per day: <strong>${pricePerDay}</strong></p>

        <p>Total price:
        <strong>GH₵${totalPrice.toLocaleString()}</strong></p>

        <p>📞 We will contact you at ${phone}</p>
    `;

});
// =========================
// CAR FILTER
// =========================

function filterCars(category) {

    const cars = document.querySelectorAll(".car-card");

    cars.forEach(function(car) {

        if (
            category === "all" ||
            car.dataset.category === category
        ) {
            car.style.display = "block";
        } else {
            car.style.display = "none";
        }

    });
}
function toggleMenu() {
    const menu = document.querySelector(".nav-links");
    menu.classList.toggle("active");
}