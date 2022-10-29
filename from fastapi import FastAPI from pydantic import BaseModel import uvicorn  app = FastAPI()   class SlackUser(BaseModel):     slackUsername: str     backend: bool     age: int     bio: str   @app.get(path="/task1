from fastapi import FastAPI
from pydantic import BaseModel
import uvicorn

app = FastAPI()


class SlackUser(BaseModel):
    slackUsername: str
    backend: bool
    age: int
    bio: str


@app.get(path="/", response_model=SlackUser)
async def getUserSlackUser() -> SlackUser:
    return SlackUser(
        slackUsername="Munanomy",
        backend=True,
        age=20,
        bio="I like cats.",
    )


def dev():
    uvicorn.run("sample_server.main:app", reload=True)
