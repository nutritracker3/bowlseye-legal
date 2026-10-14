---
title: Join on bowlseye
---

# Join me on bowlseye

A friend invited you to compete on streaks and protein.

<p><a id="open" href="#" style="display:inline-block;padding:14px 26px;border-radius:30px;background:#221E1B;color:#FFF7F0;text-decoration:none;font-weight:700">Open in bowlseye</a></p>

<p id="note">Tap the button on a phone that has bowlseye installed. bowlseye is coming to Google Play and the App Store: once it is there, this page will link to it.</p>

<script>
(function () {
  // The invite code travels in ?c=. It must look exactly like a code the server makes (16 characters, no 0/O/1/I): anything else is not an invite.
  var m = /[?&]c=([^&]+)/.exec(location.search);
  var code = m ? decodeURIComponent(m[1]).toUpperCase() : '';
  var link = document.getElementById('open');
  if (/^[A-HJ-NP-Z2-9]{16}$/.test(code)) {
    link.href = 'bowlseye://invite/' + code;
    // Installed app: try to open it straight away. Browsers may block this without a tap, so the button stays as the fallback.
    setTimeout(function () { location.href = link.href; }, 300);
  } else {
    link.style.display = 'none';
    document.getElementById('note').textContent = 'This invite link looks incomplete. Ask your friend to send it again.';
  }
})();
</script>
