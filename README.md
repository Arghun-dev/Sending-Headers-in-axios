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



So you should send data in this type in **axios.get**

without body and with body does not have difference

```
export const userProfileImage_Get = (token) => dispatch => {
    axios
        .get(`${API_BASE_ADDRESS}Users/UserProfileImage_Get`, { headers: { 'Token': token } })
        .then(res => {
            dispatch({
                type: USER_PROFILE_IMAGE_GET,
                payload: res.data
            })
        })
}



AND


export const getusermenulist = (SystemId, token) => (dispatch) => {
  axios
    .get(
      `${API_BASE_ADDRESS}Users/UserMenu_List?UserId=0&SystemId=${SystemId}`, { headers: { 'Token': token } }
    )
    .then((res) => {
      dispatch({
        type: GET_USER_MENU_LIST,
        payload: res.data,
      });
    })
    .catch(err => {
      console.log(err)
    })
};
```
