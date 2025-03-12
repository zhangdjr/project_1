# Bitcoin Block Hashing Process

## Data Table

| k  | xD                                      | Hash                                                                | Time (s) | Trials     |
|----|-----------------------------------------|---------------------------------------------------------------------|----------|-----------|
| 2  | 1450081131this_is_a_bitcoin_block_of_62321234 | 00a0c454380483174fe3075839163091b90cf90a55c0cdc1cd126db4c73dd06f  | 1        | 10,000    |
| 3  | 1655663793this_is_a_bitcoin_block_of_62321234 | 0000dac1581541a743ac79e6e5814438b4d055c0468d257dc2127b5d5bc079ce  | 1        | 30,000    |
| 4  | 719498601this_is_a_bitcoin_block_of_62321234 | 0000417ae5759c448e0fed78763ba1f366af88614d88cc756cf2cd6adb9225ac  | 1        | 50,000    |
| 5  | 182792973this_is_a_bitcoin_block_of_62321234 | 000009ef410812f54e1d0ebd1445f7a2248caea5ba5eb0d5ea8b4369e3b2dc85  | 1        | 100,000   |
| 6  | 767710983this_is_a_bitcoin_block_of_62321234 | 00000005105b1a08b3f748fed406ccbb90304f02a17d18aefc5de9bfebd5106d  | 4        | 10,000,000 |

## Explanation of Trials

The number of trials was determined through trial and error. If I didn't get the desired hash, I simply increased the number of trials significantly.

## Code Change

I modified the following line:

```scala
val nonce = sc.range(0, trials).mapPartitionsWithIndex((indx, iter) => {
    val rand = new scala.util.Random(indx + seed)
    iter.map(x => rand.nextInt(Int.MaxValue - 1) + 1)
})
```

to:

```scala
val nonce = sc.range(0, trials)
```

## Screenshot

![Screenshot of the process](https://github.com/user-attachments/assets/f0dd3d94-402d-4f14-9fa6-eb68f93a37ab)

