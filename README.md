# use-instagram-feed

To install:
- `npm i use-instagram-feed`
  
or

- `yarn add use-instagram-feed`

To use, pass the:

- instagram user id: string (I have used [this online tool to find user ids](https://codeofaninja.com/tools/find-instagram-user-id))
- thumbnailWidth: number
- photoCount: number
  
```js
import {useInstagramFeed} from 'use-instagram-feed'

const App = () => {
  let photos = useInstagramFeed({
    userId: "10972317574",
    thumbnailWidth: 640,
    photoCount: 12,
  })

  return (
      <div>
      {photos &&
        photos.map(({ id, caption src, width, height, url }) => (
          <a key={id} href={url}>
            <img src={src} alt={caption} />
          </a>
        ))}
    </div>
  )
}

export default App
```

The hook returns each photo's id, caption text, photo source, photo width & height, and the post's URL
