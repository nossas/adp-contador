# adp-contador

<div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div>
<script>
  setTimeout(() => {

    fetch("/api/plip-counter/", {
      method: "GET",
      headers: {
        "Content-Type": "application/json",
      },
    })
      .then((response) => response.json())
      .then((data) => {
        const confirmed_signatures =
          data.data.data.plip_signatures_aggregate.aggregate.sum
            .confirmed_signatures;
        const expected_signatures =
          data.data.data.plips_aggregate.aggregate.sum.expected_signatures;
        console.log("Success:", confirmed_signatures);
        console.log("Success:", expected_signatures);
        document.querySelector(
          "#block-39764 > div:nth-child(1) > div:nth-child(1) > div:nth-child(1) > div:nth-child(1) > div:nth-child(1) > div:nth-child(1) > div:nth-child(1) > div:nth-child(2) > span:nth-child(1) > span:nth-child(1) > span:nth-child(1) > span:nth-child(1) > span:nth-child(1)"
        ).textContent = new Intl.NumberFormat().format(
          confirmed_signatures + expected_signatures
        );
      })
      .catch((error) => {
        console.error("Error:", error);
      });
}, "1000")
</script>
