# Sending-Headers-in-axios

### Sending Headers in axios post request

**Always Remember the axios get 2 parameters: the first is: body and the second is: headers**

So you should send data in this type in **axios.post**

```
export const logout = (token) => (dispatch) => {
  const data = null

  axios
    .post(`${API_BASE_ADDRESS}Users/UserLogOut`, data, { headers: { "Token": token } })
    .then((res) => {
      dispatch({
        type: LOGOUT_SUCCESS,
        payload: res.data
      });
    })
    .catch((err) => {
      console.log(err);
    });
};
```

As you can see in this example because we don't have body we should send the body as **null**.

**This is important that you have to send headers as second parameter not the first**
