# cli cup

Helps me deploy my site to AWS S3.

Requires `awscli` and stores your credentials using `aws configure`, so if you already have a profile in there it'll be reused.

## Usage

### Installation

````
brew install awscli
```

Clone this repo and make sure `cup` is an executable and in your path (I symlink it into my `~/bin`).

### Setup

I set my site up like this:

```bash
cd DIR_OF_PROJECT
cup init
# enter site details and aws details
```

My project root contains a directory which is the repository of my site. Since I don't want to expose my AWS profile handle and bucket name I init cup (and therefore place the `.cup` file) in the directory above the git root.

If you initialise cup with the `dir` set to `.` and there's a `.gitignore` file, `cup init` will amend the file with a line ignoring `.cup`.

### Deploy

```bash
cup up --dry
cup up
```


## Tips

- Make sure you set the right region in the aws config unless you use the standard S3 region. If you want to amend this later (aws will complain), use `aws --profile PROFILE_NAME configure`.
- I recommend initialising cup in the directory containing your "webroot", so that you don't accidentally commit the `.cup` file (which doesn't really contain anything secret, but I prefer to be on the safe side).


## Future

The tool in this repository will be kept simple.

Elsewhere I'm working on a more visual experience, I guess you could call it an offline static site cms.

## LICENSE

[MIT](./LICENSE.md).