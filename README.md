# Mediator
>is an asynchronous library that implements CQRS pattern in your Python applications

## Example Command & Query
```
@dataclass
class UserCreate(Command):
    id: int
    user_name: str

@dataclass
class UserCreateResponse:
    id: int

class UserCreateHandler(CommandHandler[UserCreate, UserCreateResponse])

    def __init__(self) -> None:
        ...

    async def handle(self, command: UserCreate) -> UserCreateResponse:
        # ur logic
        return UserCreateResponse(command.id)

```