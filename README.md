// Check password
function checkPassword() {
  const input = document.getElementById("password-input").value;
  if (input === "cidler6901") {
    editable = true;
    document.getElementById("lock-screen").style.display = "none";
    document.getElementById("todo-input").disabled = false;
    document.getElementById("add-btn").disabled = false;
    document.getElementById("notes").disabled = false;
    document.getElementById("logout-btn").style.display = "inline";
    document.getElementById("readonly-banner").style.display = "none"; // hide banner
    refreshTasks();
  } else {
    document.getElementById("error").innerText = "❌ Wrong password!";
  }
}

// Logout
function logout() {
  editable = false;
  document.getElementById("todo-input").disabled = true;
  document.getElementById("add-btn").disabled = true;
  document.getElementById("notes").disabled = true;
  document.getElementById("logout-btn").style.display = "none";
  document.getElementById("lock-screen").style.display = "flex";
  document.getElementById("readonly-banner").style.display = "block"; // show banner
  refreshTasks();
}
<!-- Read-only Warning Bar -->
<div id="readonly-banner">
  🔒 Read-only mode – enter password to edit tasks & notes
</div>
#readonly-banner {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background: #ff9800;
  color: white;
  text-align: center;
  padding: 0.8rem;
  font-weight: bold;
  z-index: 10000;
}
body {
  margin-top: 50px; /* pushes page content down so it’s not under the banner */
}
