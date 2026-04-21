# praia-dotenv

Load environment variables from `.env` files in [Praia](https://github.com/praia-lang/praia). Parses the file and sets each variable via `sys.setenv()`.

## Install

```bash
sand install github.com/viggou/praia-dotenv
```

## Usage

```praia
use "dotenv"

dotenv.load()

print(sys.env("DATABASE_URL"))
print(sys.env("SECRET_KEY"))
```

### Loading a specific file

```praia
dotenv.load(".env.production")
```

### Parse without setting

```praia
let vars = dotenv.parse()
print(vars.DATABASE_URL)
```

## API

| Method | Description |
|--------|-------------|
| `load(path?)` | Parse the file and set each variable via `sys.setenv()`. Returns a map of all parsed variables. Defaults to `".env"`. |
| `parse(path?)` | Parse the file and return a map without setting environment variables. Defaults to `".env"`. |

## .env format

```bash
# Comments are supported
DATABASE_URL=postgres://localhost/mydb
SECRET_KEY=supersecret

# Quoted values (single or double)
MESSAGE="hello world"
GREETING='hi there'

# Inline comments on unquoted values
PORT=3000 # the server port

# Empty lines are skipped
```

## License

MIT
