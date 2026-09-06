function dailyLog163() {
  const sessions = [
    { subject: "JavaScript", minutes: 45 },
    { subject: "Git", minutes: 30 },
    { subject: "Algorithms", minutes: 50 },
    { subject: "English", minutes: 25 }
  ];

  const totalMinutes = sessions.reduc(
    (sum, session) => sum + session.minutes,
    0
  );

  const mostStudied = sessions.reduce((max, session) =>
    session.minutes > max.minutes ? session : max
  );

  const report = {
    date: new Date().toISOString().split("T")[0],
    totalStudyTime: `${totalMinutes} minutes`,
    sessions: sessions.length,
    mostProductiveSubject: mostStudied.subject,
    longestSession: `${mostStudied.minutes} minutes`
  };

  console.log("Daily Study Report:", report);
}

dailyLog163();
