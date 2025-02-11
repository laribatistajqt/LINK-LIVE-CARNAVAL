<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Adicionar à Agenda</title>
    <script>
        function redirectToCalendar() {
            const googleCalendarURL = "https://calendar.google.com/calendar/render?action=TEMPLATE&text=Nome+do+Evento&dates=20250301T190000Z/20250301T220000Z&details=Detalhes+do+evento&location=Local+do+Evento";
            const outlookCalendarURL = "https://outlook.live.com/calendar/0/deeplink/compose?subject=Nome+do+Evento&startdt=2025-03-01T19:00:00Z&enddt=2025-03-01T22:00:00Z&body=Detalhes+do+evento&location=Local+do+Evento";
            const appleCalendarURL = "evento.ics"; // Crie um arquivo ICS e hospede-o online

            const userAgent = navigator.userAgent.toLowerCase();

            if (userAgent.includes("android") || userAgent.includes("gmail") || userAgent.includes("google")) {
                window.location.href = googleCalendarURL;
            } else if (userAgent.includes("windows") || userAgent.includes("outlook")) {
                window.location.href = outlookCalendarURL;
            } else if (userAgent.includes("iphone") || userAgent.includes("ipad") || userAgent.includes("mac")) {
                window.location.href = appleCalendarURL;
            } else {
                window.location.href = googleCalendarURL; // Padrão para Google Calendar
            }
        }
    </script>
</head>
<body onload="redirectToCalendar()">
    <p>Redirecionando para seu calendário...</p>
</body>
</html>
