def dirReduc(arr):

  res = [1 if item == 'NORTH' else item for item in arr]
  res = [-1 if item == 'SOUTH' else item for item in res]
  res = [2 if item == 'EAST' else item for item in res]
  res = [-2 if item == 'WEST' else item for item in res]
  res.append(9)
  print (res)
  aa = res
  print (aa)
  x = 0
  while(x<len(aa)):
      if aa[x] == 9:
          break
      elif aa[x] + aa[x+1] == 0:
          aa.pop(x)
          aa.pop(x)
          x=0
      else :
          x = x+1
  print(aa)

  ans = ['NORTH' if item == 1 else item for item in aa]
  ans = ['SOUTH' if item == -1 else item for item in ans]
  ans = ['EAST' if item == 2 else item for item in ans]
  ans = ['WEST' if item == -2 else item for item in ans]
  ans.pop()
  print (ans)
  return ans
