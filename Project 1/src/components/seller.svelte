<script>
    const sellers = [
      {
        title: 'Top Sellers',
        data: {
          sold: '1,542 plants sold',
          count: '10 sellers',
          time: '7 days',
          avatars: ['/avatar.png', '/avatar.jpg', '/avatar.png', '/avatar.jpg'],
        },
      },
      {
        title: 'Featured Sellers',
        data: {
          sold: '2,156 plants sold',
          count: '10 sellers',
          time: '7 days',
          avatars: ['/avatar.jpg', '/avatar.png', '/avatar.jpg', '/avatar.png'],
        },
      },
    ];
  </script>
  
<div class="container mx-auto py-8 bg-fade">
    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 px-4 py-8">
        {#each sellers as seller}
          <div class="bg-white shadow-md rounded-lg p-4">
            
            <div class="flex justify-between items-center">
              <h2 class="text-lg font-bold text-green-700">{seller.title}</h2>
              <a href="#" class="text-sm text-green-500 hover:underline">View All →</a>
            </div>
      
           
            <div class="flex items-center mt-4 space-x-4">
             
              <div class="flex -space-x-2">
                {#each seller.data.avatars as avatar}
                  <img
                    src={avatar}
                    alt="Avatar"
                    class="w-10 h-10 rounded-full border-2 border-white"
                  />
                {/each}
              </div>
      
              
              <div>
                <p class="text-sm font-medium text-gray-800">{seller.data.sold}</p>
                <p class="text-xs text-gray-500">{seller.data.count}</p>
                <p class="text-xs text-gray-500">{seller.data.time}</p>
              </div>
            </div>
          </div>
        {/each}
      </div>
</div>