# Contadores da Amaz

```jsx
<script>
  setTimeout(() => {

fetch("/api/plip-counter/", {
  method: "GET",
  headers: {
    "Content-Type": "application/json",
    "Cache-Control": "no-cache"
  },
})
  .then((response) => response.json())
  .then((data) => {
    const confirmed_signatures =
      data.data.signaturesTotal.data.plip_signatures_aggregate.aggregate.sum.confirmed_signatures;
    const expected_signatures =
      data.data.signaturesTotal.data.plips_aggregate.aggregate.sum.expected_signatures;
    console.log("Confirmed Signatures:", confirmed_signatures);
    console.log("Expected Signatures:", expected_signatures);
    document.querySelector(
      "#block-39884 > div:nth-child(1) > div:nth-child(1) > div:nth-child(1) > div:nth-child(1) > div:nth-child(1) > div:nth-child(1) > div:nth-child(1) > div:nth-child(2) > span:nth-child(1) > span:nth-child(1) > span:nth-child(1) > span:nth-child(1) > span:nth-child(1)"
    ).textContent = new Intl.NumberFormat().format(
      confirmed_signatures + expected_signatures
    );
    document.querySelector(
      "#block-39884 > div:nth-child(1) > div:nth-child(1) > div:nth-child(3) > div:nth-child(1) > div:nth-child(1) > div:nth-child(1) > div:nth-child(1) > div:nth-child(2) > span:nth-child(1) > span:nth-child(1) > span:nth-child(1) > span:nth-child(1) > span:nth-child(1)"
    ).textContent = new Intl.NumberFormat().format(
      confirmed_signatures
    );
  })
  .catch((error) => {
    console.error("Error:", error);
  });
}, "1000")
</script>
```
