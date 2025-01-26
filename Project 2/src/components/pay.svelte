<script>
    let member ='';
    let paymentMethod ='';
    let sendOn = '';
    let dueOn = '';
    let paymentCollection = 'now';

    let items = [
        { detail: "Kids Basic Karate", amount: 99},
        { detail: "Youth Basic Membership", amount: 299},
        { detail: "Women  Membership", amount: 999},
        { detail: "Women Adv Membership", amount: 2199},
        { detail: "Men Excl Membership", amount: 5999}

    ]

    const addItem =() =>{
        items = [...items,{detail: "", amount: 0}];
    };

    const totalAmount = () => items.reduce((sum, item) => sum + item.amount,0);
</script>

<div class="w-full max-w-lg mx-auto p-6 bg-white rounded-2xl shadow-lg">
    
    <h2 class="text-xl font-semibold mb-2">Create Payment</h2>
    <p class="paragraph">Transact securely, with us : trusted branch</p>

    <div class="space-y-4">

        <div>
            <label class="form-label">Member</label>
            <select bind:value={member} class="form-input">
                <option value = "">Select to whom you need to send this invoice</option>
            </select>
        </div>


        <div>
            <label class="form-label">Payment Method</label>
            <select bind:value={paymentMethod} class="form-label">
                <option value="">select payment method</option>
            </select>
        </div>

        <div class="grid grid-cols-2 gap-4">
            <div>
                <label class="form-label">Send On</label>
                <input type="date" bind:value={sendOn} class="form-input" />
            </div>
            <div>
                <label class="form-label">Due On</label>
                <input type="date" bind:value={dueOn} class="form-input" />
            </div>
        </div>

        <div>
            <label class="form-label">Payment Collection</label>
            <div class="space-y-2">
                <label class="flex items-center space-x-2 bg-fade p-2">
                    <input type="radio" bind:group={paymentCollection} value="now" class="radio-input" />
                    <span>Now</span>
                </label>
                <label class="flex items-center space-x-2">
                    <input type="radio" bind:group={paymentCollection} value="email" class="radio-input" />
                    <span>Send Invoice via Email</span>
                </label>
            </div>
        </div>

        <div>
            <label for="form" class="form-label">Items</label>
            <div class="space-y-2">
                {#each items as item, index}
                    <div class="flex items-center space-x-4">
                        <input type="text" bind:value={item.detail} placeholder="Item Detail" class="item-input">
                        <input type="number" bind:value={item.amount} placeholder="amount" class="item-input">
                    </div>
                {/each}
                <button on:click={addItem} class="text-indigo-600 text-sm">
                    + Add New Item
                </button>
            </div>
        </div>

        <div class="flex justify-between items-center pt-4 border-t">
            <span class="text-lg font-semibold">Total</span>
            <span class="text-lg font-semibold">${totalAmount()}</span>
        </div>
    </div>

    <div class="flex justify-between mt-6">
        <button class="cancel-btn">Cancel</button>
        <button class="send-btn">Send</button>
    </div>
</div>