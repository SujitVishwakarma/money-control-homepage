<script>
    export let items = [];
  </script>
  
  <div>
    <table class="min-w-full bg-white border border-gray-200">
      <thead>
        <tr>
          <th class="py-2 px-4 border-b">Equity</th>
          <th class="py-2 px-4 border-b">Type</th>
          <th class="py-2 px-4 border-b">Issue Price</th>
          <th class="py-2 px-4 border-b">Issue Size</th>
          <th class="py-2 px-4 border-b">Lot Size</th>
          <th class="py-2 px-4 border-b">Issue Open</th>
          <th class="py-2 px-4 border-b">Issue Close</th>
        </tr>
      </thead>
      <tbody>
        {#each items as item}
          <tr>
            <td class="py-2 px-4 border-b">{item.equity}</td>
            <td class="py-2 px-4 border-b">{item.type}</td>
            <td class="py-2 px-4 border-b">{item.issuePrice}</td>
            <td class="py-2 px-4 border-b">{item.issueSize}</td>
            <td class="py-2 px-4 border-b">{item.lotSize}</td>
            <td class="py-2 px-4 border-b">{item.issueOpen}</td>
            <td class="py-2 px-4 border-b">{item.issueClose}</td>
          </tr>
        {/each}
      </tbody>
    </table>
  </div>
  