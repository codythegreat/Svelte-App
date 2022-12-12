<script>
  export let count = 1;
</script>

<div>{count}</div>

<style>
  div {
    cursor: default;
    width: 32px;
    height: 32px;
    border: 3px solid #333;
    border-radius: 4px;
    background: white;
    color: black;
    font-weight: bold;
    font-size: 1.2rem;
    text-align: center;
    line-height: 32px;
    position: absolute;
    top: -8px;
    right: -8px;
  }
  @media (max-width: 768px) {
    div {
        width: 20px;
        height: 20px;
        border: 3px solid #333;
        border-radius: 50%;
        top: 8px;
        right: 8px;
        line-height: 20px;
    }
  }
</style>