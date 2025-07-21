1. "get_key" query from client
2. websocket service checks `keys` table for entries whos `UsedAt` column is empty
3. if found, it sends this key to user
4. if not, generate new key, store in `keys` table and send key to user