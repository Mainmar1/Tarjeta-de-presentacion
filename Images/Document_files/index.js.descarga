const getRemainTime = (deadline) => {
  let now = new Date(),
    remainTime = (new Date(deadline) - now + 1000) / 1000,
    remainSecond = ("0" + Math.floor(remainTime % 60)).slice(-2),
    remainMinutes = ("0" + Math.floor((remainTime / 60) % 60)).slice(-2),
    remainHours = ("0" + Math.floor((remainTime / 3600) % 24)).slice(-2),
    remainDays = Math.floor(remainTime / (3600 * 24));

  return {
    remainTime,
    remainSecond,
    remainMinutes,
    remainHours,
    remainDays,
  };
};

const countdown = (deadline, element, finalMessage) => {
  const el = document.getElementById(element);

  const timerUpdate = setInterval(() => {
    let time = getRemainTime(deadline);
    el.innerHTML = ` ${time.remainDays}D ${time.remainHours}H ${time.remainMinutes}M ${time.remainSecond}S`;

    if (time.remainTime <= 1) {
      clearInterval(timerUpdate);
      el.innerHTML = finalMessage;
    }
  }, 1000);
};

countdown("Nov 19 2022 11:00:00 GMT-0300", "clock", "Final del mensaje");
