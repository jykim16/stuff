## When using git, what do people mean when they talk about "the SHA-1"? How is that related to how git works?

Git is designed to provide an absolute assurance that one person's version of a given codebase is exactly the same as another person's version of a given codebase, at the same revision.

In order to provide this assurance, Git relies heavily on hashing both data (the files themselves) and metadata (such as commit descriptions).

### What's hashing

Remember what "hashing" is -- it's converting an arbitrarily-large input to a small (fixed-length) output in a one-way manner. This is different from encryption, in that an encrypted item can be decrypted.

Git uses the SHA-1 hashing mechanism. SHA-1 converts any string into a 40-digit hexadecimal number.

### Git hashes the world

Using SHA-1, git hashes all kinds of things. It hashes the files themselves, it hashes the directory trees that those files live in, it hashes previous commits, it hashes the current commit, and various other bits of metadata.

At each pass of processing, it keeps feeding those hashes in as inputs into other hashes, recursively.

In the end, you get a single commit hash, that represents the full "state of the world" at that time.