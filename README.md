# CycleGAN-with-MNIST

## MNIST Digit Conversion from 4 to 9 using CycleGAN

* In this Notebook we'll convert digit 4 to digit 9 and vice versa using Cycle GAN Network.
* We'll use MNIST dataset for this project.
* Below is the result that we want to achieve using CycleGANs.

<center>

![4to9.png](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOgAAACDCAIAAAAI+MC2AAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAADsMAAA7DAcdvqGQAABSiSURBVHhe7Z1pcBVVm4C99yYhCRB2BEUFZdOkEBUVlQLHHVdwcKGUQooRUVxLQC21ENHhww0dLB0RRMXCQkdlcEFGRSGCCgglKIIwENEJqBAcIhJBzLzc85ye/khzuSfdN8vH+/zq2+m3l/c8ffr06dOdQyoVpR6i4ir1EhVXqZeouEq9RMVV6iUqrlIvUXHrMYMHD7733ntlYsGCBZ07dzYzI+GQQw5Zu3YtP+okYcU96qijPvjgA36EZsyYMddccw0//p5oN1TryOHk5uY2bNiwdevW4l95eTl/cMETNzXTpk0744wz+JEegeL26dPn+eef50dto+LWDt7h/Pjjj4WFhXfddZeZb9i9ezdTKVFxq49XACY7d955Z9OmTdu3b//ee++ZBeRo77777pNPPrlx48aXXnrp1q1bZebHH398+OGHmwUEs5I5c+ZkZ2dnZWVJPdStWzf+ZvFv6PTTT7/99tubNGnSoUOHhQsXypx27dq1atXqxRdfNAu/88473bt3ly3KfDkZzEzhpZdeOvLII5s3b/7ggw96K9yzZ8/48eOPPvpomX/FFVeYPcw03taFkSNHXnTRRTIhujz99NMdO3aUBMrPt99++/jjj5fDPO2007766qvkspXLli074YQTGjVqdOWVV1511VVGXH8+N27c2L9//5YtW8rhjBgxYtWqVQ0aNIjH45JVWZUsUFFRIcV0xBFHSGV/ww03/P777ybwkUceadOmTdu2badOnZpaXLO5CRMmSM4l5K233nr33Xc7derUrFmzhx9+2Cz8xRdf9OzZU7YoC8hu/PHHH2b+3LlzpVVTUFBw44039u7d2zsTZKNdu3YVec4777ySkhIzMwVRiivOTZ48+c8//3zmmWfk+P/66y+ZL0d72GGHrVy58rfffrv88stNhRoorkykU+PKhhKJxAsvvCAbkmKTArjpppukMCQjUpzmmivrX7FihRgp5S3FI5mVmd98840UXnFxsSRRSk721qzwySefPPXUU3/44QdZybBhw66++mqZmWm8wxHPjjvuuPvuu0+mRZdzzjlHzhyRSQQVLT7//HM5TDkhZXnZPdlzOfGeeOKJXbt2vf7663II+4grC8s5L2e1ZHvnzp1ysDLT1CkyYZC/XnLJJbKV7du3X3zxxVKtyEypNSRRppgGDhx4QHGlCMaOHSu7ISUuJ4mEyNq+/vpraf+sX79ellm6dOlnn30ml44NGzaIkRMnTpSZv/zyi9Qmb7zxhsyXtMv+mxXOmjXrmGOOkXNM5o8bN05OVJmZmijFlW2bmTt27JAj37Rpk0zL0XrXQVFH6lRJbkhxpU4yM8VO2dDmzZvNT6ljli9fbqY9brvtNikqmZBEe1LKHsqemBVKWj/88EMzv7S0VLKZ5pU6DHI4pgoUEaXuMdWeHMtHH31kFhg+fLix2SC11CeffDJ//nyvRhCkgPcRd9GiRaLRPvvvF1di8/Pz161bZ37K8qZ2HzJkiFdMa9asOaC4IqiUo0yLr7KwnGDJRSpPPPFEU034EWv79esnE3LFk2rYzJQ9keuhWeEFF1wwZcoUM1+qm7y8vANWuhE3FcxMwTtyOVq5/JmZcjYbz0KK621INiErNNOCrNPUMZLHM888U4pQLklyobz22mtlplwWR40alVxwL3IJMyuUNEk1IA4ZZHlpd5plMod3OH7kWL777jsz3bdvX9kx9qlJE5meMWPGq6++2qNHD7OAIOfhPuLOnDnzpJNOSv7x//Fn7KeffpKtsNImTSQ/cv7I/PPPP98rJqnaveLz4xfXKz45SWRhqVbNT9nQ9OnTZULsl/bPoYceKrmVne/Vq5fMlCaZNMaSC+5FJDYrPPbYY81pbJCzQlqAZpn9URPieqeyXAtMjbt48WJpD5mZ8lPqALOSBx54IBJxpcEq11O5Vsq01LhmnbJyuaLtXa6yUmo4r8aVyuzTTz8182uM/Ynr6SKNloceeshMe0il669xpa1ftcaVBsY+Na60NLyMmfqs6pl53XXXecUkJ094cc866yxpj0l9LNNS45odkD3xmgH+Glfata+88oqZnyY1Ia4cpDQS5Oo8YMAAo86vv/4q6ZNbKGkkiU/SYDIrefbZZ2Ulkty9q/h7nMT1btTkFkGmjbjSApNGsJzK0lIcPXq018YVxWUnzbXp559/lvaWTGSaA4q7ZMkSKVe5dEgBy5VKciUSyJ5Lm15ah5I3aSnur40rxpg2rjkhpf0qm/Nuj2699Vap9qTqlWkx+P3335cJuZmW2tEUk6QrvLhyOy5tM9n5b7/9VqoGU2TSxpUikLaERE2aNMlr47755puFhYVSQDItbrz22msykZqaENfrVZBbAdl1s4AsLxdrserRRx/1VrJlyxZZidxayo2zWczDSVy5cZG2o+RIrlZyS+vV4hIrBW96FeSWccGCBTJTzpPHH39ckivLS1V9zz33mIUzygHFFUQ4aRjIpVMSJee8qb1E6O7du8uuXplkH3GF77///rLLLpNjbNGixS233CJzRNkLL7xQLnEyR36K0HKMHTp0kBKR9v1TTz2VjNt7HRd30+9VMDP3J640x7t06SINAGkk3H///V6RyUF16tTJ9CpIU+Hll18282WiqKhIdklOV2lwm5kpCCvuAfGOtk5RXl4u1by5/1VqBakv5CSZN28evx05uMSdPXu2XArlMio3alJveY1FpcaQlsm2bdvk/m/cuHFyJfF6kV05uMQdOnSoXHnlOiW3DqtXr2auUoOMGTNGmjHS1DnllFO8TrRqkHFxFSUTqLhKvUTFVeol+xX3ECUNSJY7MQsrUnyQmliMZAWh4oaCZLlDyai4QZAaFTdzkCx3iFdSQrKCUHFDQbLcIV5JCckKQsUNBclyh3glJSQrCBU3FCTLHeKVlJCsIFTcUJAsd4hXUkKyglBxQ0Gy3CFeSQnJCkLFDQXJcod4JSUkKwgVNxQkyx3ilZSQrCBU3FCQLHeIV1JCsoJQcUNBstwhXkkJyQpCxQ0FyXKHeCUlJCsIFTcUJMsd4pWUkKwgalTcbAtjKDI5xCTP0tFynqWfj76WdpaEhRWlhGS5Q/w/OhSzD/6QHiQrCBUX0FbFjRSK2Qd/SA+SFYSKC2ir4kYKxeyDP6QHyQoiU+Kym7FYWx/dLc0sLB0dcctxlicspZb/9VFiudrSyMIaU0Ky3CE+w1AGsRhJ8cEfgv7kwRKxGKdyIsEf4nFqIF8d5JHlgzBfIAulZzDJCkLFBbRVcX2whIqLtiquilvXxGWnYrGmlid9zLf0sRAWHWy1adNhlnLL75aZPiZb/smCtvVQXFTKzs63FFiSH0HcS2NLgyoQ7CPHwloKCtpY2ltYXePGqOqTVWBF2dloq+LuD7aq4iZBNxX3gLBTKu6BID5ScETFrQYtLLdZynyss5xtISw66Nzq23ehBW3Ly+dYyH0SSjg/n6xnZbGi9CBZ7hBfXSj8WAx9ktxtmW2ZZPnIQs0xf/4nFhadPXuR5QvLYgv3ASUl6y3Flv4WDM3OZhejgGQFoeIC2qq4Kq4BZ5OgrYqr4qYHyQpCxQW0VXEPTnG7WjZY9viYbimyEBYdPMnt12+ZBW3Ly2dZuPlKQlh1IVnuEO8IamRn8xS7Y8ePfWy2cMDl5Sssyy2rLWstlNOGDVss/N6wAW0XLyZ4+XJ6wktLSe6yZVMtPGHPy2Nfo4BkBaHihoJkuUO8I2ir4qq4hFUXkuUO8Y6grYoblbjNLddZUHXPnl0+Bll44JuBR75o6xN3u4We25kzG/ogrLqQLHeID4LWqw86RROJQstcC1lOwp1EWdnblokWKozp08daRliGW1h04sQxlsEWFh0xAtnXrqXNW1KyxNLKwmFEAckKQsUNBclyh/ggsNUH2qq4PlTcUJAsd4gPAlt9oK2K6yMacWnYdu06xbLbQqdLEhq2RUWUQ3qDtZ1AW5+4mywjLTziTEJYdSFZ7hAfBLb6hllhRKtW/26hDVtevtXH9ZbeFgbjde9O3ouKWltYY6tWPMwtKKAuadaM5n+jRpzcDRseZfkPC83hLVs4V8rKelh4tpuEQ6ouJCsIFTcUJMsd4oNAWxVXxTWgrYqbhDUenOKS16wsnoOdffaXlp2W0T5aWoiPDkYx5eQMtdAEKylZY6Ewe/dmp5MQX11IljvEB8E5nUjkWmhpDh7Mg8d16yos1BNJeGmuXTuOLSWYlXK0uAdPF/PzaQ4PH06vWGnpRgtVV9eurC4Jh1RdSFYQKm4oSJY7xAeBPiquimtAWxU3CUoenOLyqCQvb4CFoykt3WHBoySM8W7alPjooMTatXvEQsFWVNBbk/wv+gaSmoT46kKy3CE+CPYsFuMpWXY2yR0wgCdavqdcnX1gWeiWJZv3vY5Gm7dRI7ozBw2iV2ztWsbaFBdTJ7VsSUwS1lhdSFYQKm4oSJY7xAfBnqm4Kq6BJVTcA8Hm/4HFpV2Zk3O+hTEdK1b8YaH9leQIC/HRca7lPQvdReXljDadPZtFI4VkuUN8SmhyJhK8oNenz0oLx1ZefroPZMmAuAyybtGCZ2sTJzKcZ/NmtC0upk5q2pTgJKyxupCsIFTcUJAsd4hPCdqquEGouKEgWe4QnxK0VXGDCCWuB++OtG8/3sK4jz17Vvk41YLvOTnEh4ZRIWPGbLP8t2WUhUUjhWS5Q3x68CGgtm1prS9ZwqilXbse80GLOPTLM0gXi1FIOTk8disqYjDv6tU8rNu69X0LD9lCj1vyQ7KCUHFDQbLcIT490FbF9aHihoJkuUN8eqCtiusjGnH5mEnjxrzx2b8/Q2x278bfJNMsjCotLCQ+NJwu48fzvG7nThqDK1cOtLBopJAsd4hPD3zMzqZbcehQErpnD48HkwyxoFt16wUatvE4X79p0oT1Dhnyk4WRNWVl91toj0c6cIpkBaHihoJkuUN8eqCtiutDxQ0FyXKH+PRAWxXXRzTicqDxOJ/ZaNPmFssPPuhB2bz5NcuVFsLatGGNjvzNwuOyiooPLbS+27dn0UghWe4Qnx40OWMxXpBq3vw5y//44G2euXMZlnv99VQnjRtTPI49ZTwXzcubYOF53ZYtfFZk/nw6ODPQxSmQrCBU3FCQLHeITw+0VXF9qLihIFnuEJ8eaKvi+ohGXA+aOYnE4ZZ7fNArtmoV/m7ezOs1y5bx7unYsQwY6dyZFaVsM/G47Nxz/8vyveVfLTT3out680Oy3CHeEeyLx/G3efOnfPAIq7h4noV3c0eM6GLZO7w3CSvywcnhG9zDuzg9evynhb7Gbdv+xcLw3tAjmwMhWUGouKEgWe4Q7wiKqbgqbkhIljvEO4JiKm7k4nqQjHicBmYSsjhiBHmdN48+Fd8XSOkwmzaNL+EPG8ZXsjp2ZI3xOK+lFhQw4mPiRF7k3bSJltf8+ZdY2KHMQLLcIb66cE4nErzFm+RRC/4WFzPiacUKPrA6Z85FliMtvO7coAHt2bw83gNu3Zr/MjB5Mv1tJSW8prNxI92ZhYUUSeiRPYGQrCBU3FCQLHeIry5oq+JWhdDqwtGouPuB+OqCtipuVQiNFAZ1tmjxzxY+UTl1KmM3Vq+mDbVtGw++Vq7ko9qTJt1s4VHYwIF8dHzhQvrAKiqmW2gpd+7MtjMDyXKH+NBgTZLDLDzmGjKEV66//PJbC6/+bNiw1EK+pk+fYcH64mLG0WzdyvtYpaV8qHXWLL4mEumXwqpCsoJQcUNBstwhPjQ4mwRtVdzIQVsVV8VND5IVRI2K60Gm43GGeRYV8VmvkSNJzKxZfAx78eLvLL9a+Ccbixb9YkHbigoayNOm0S7u2JFNZgaS5Q7xkUJvVixGj1duLn1gXbpwxt9886sWOiZXrfrcwkfHly+nMli4kPuPsjJuIDZtutVCuzj0x9dSQ7KCUHFDQbLcIT5S0FbFzRxoq+JGCtqquDUJT7dycvhoR7t251gweuTIBRa+NbJjB/taWfmzhfeJp0w5xcIGMgObd4f4DEOfWSJBR1deXk8LdwkDB/KFj0GDGLbz3HN0fZWU8CZxeTnN4aVL77Sw3khH31aFZAWh4oaCzbtDfIZBLhU3c6CtihspyKXi1go03GIxOmBateJx0IoVf1pI+XPPdbMwTiTS/9BZFZLlDvE1DvcW8Tit4NxcHkIWFPDSVf/+dEOuXMl/fdm+ne6x4uLzLCS39tKr4oaCZLlDfI2DtipuDYC2Km4UoK2KWwMw3jMrq5eFL1yuXcu3xtesoZk2aBDpzHBCPUiWO8TXAagVYjEavz17MlbaBy/uTJhwqIWY0F8HSw3JCkLFDQXJcof4OgACqriRg7YqbmZAQBU3ctBWxc0MCKjiRg7/8CU/nx7aKVN4EFlW9m8WRjVH92mcNCFZ7hBfB6A/NpHg03mPPcbj3U2bGLk3dSo3vN26UYVk5g2zqpCsIFTcUJAsd4ivA6Ctihs5aKviZga0VXEjh3/40qjRB5b1lqssqJ2fT0xNQbLcIb72oDvX9/EhHpr74P8qjh5NT29BATGZecOsKiQrCBU3FCTLHeJrDwRUcTMH2qq4kYKAKm7m4AvtDRvOrAIfWunRg0VrHJLlDvE1Dt7F44wDb9CAfzQwahR7VllJrbB+Pb2PvXrxdDg3l+ZwhgeFebBDQai4oSBZ7hBf46CtilsDoK2KGwVoq+LWADwKy86+wnKxhS+utG7NojUOyXKH+NoDE3Nz77D8buEt9RkzmlmwNZHgcVmGH5h5kKwgVNxQkCx3iK890FbFzRxoq+JGCtqquAcnJMsd4msPmrrx+HEW/L3jDl5p79KFp2RZWdhaU756kKwgVNxQkCx3iK890FbFPTghWe4QX3ugrYp7cEKy3CG+DoCSsRjdYw0a0J6t8RZtVUhWECpuKEiWO8TXAXBTxT2oIFnuEF8HwE0V96CCZLmDEbXnRF2G1MRiJCsIFTcUJMsdSkbFDYLUqLiZg2S5Q8mouEGQmuqJqyh1GRVXqZeouEq9RMVV6iUqrlIvUXGVeomKq9RLVFylXqLiKvUSFVepl6i4Sr1ExVXqIZWV/we7Lf60bz+wyQAAAABJRU5ErkJggg==)


</center>


<center>

![9to4.png](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOQAAAB/CAIAAABwlPlaAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAADsMAAA7DAcdvqGQAABS4SURBVHhe7Z15cBTVt4CdycwvOwFRUEBklQiUIqIiUqIWP1cUUBRT+lRKxa0ULUWkXBDQ54rIc6tCXLHMU59guaGCoiCCgPIARdAgCgohCQGNRDSQvOP0d/t1wzBJd3rCJJzvr55O317O/e7t0923OwfUKEojQWVVGg0qq9JoUFmVRoPKqjQaVNZGyeWXX37nnXfKxLx584444ghrZiAccMABP/zwAz9SDP+yHn744bNnz+ZHvRk3btwll1zCDzfBbmifI4eTkZGRnZ3dqlUrca6iooI/eMGWNTEvvPDCSSedxI+6EVfWAQMGPPvss/zYd6isDY19OL/88kuPHj3GjBljzbeoqqpiKiEqqzfsoFsRufXWW5s3b96hQ4f333/fWkCO8I477jjuuONyc3PPO++8LVu2yMy5c+e2bdvWWkCwVjJr1qxoNBqJRKS/Oeqoo/ibwbmhfv363XzzzXl5eR07dlywYIHMadeu3cEHH/ziiy9aC7/77ru9evWSLcp8aQDWTOGll15q3779gQceOGHCBHuFu3bteuCBBzp16iTzL7zwQmsPk429deG2224755xzZEIUefLJJ7t06SIBlJ/vvPPO0UcfLYd54oknLl++PLZszddff33MMcfk5ORcdNFFw4cPt2R1xnP9+vVDhw496KCD5HBuuOGGVatWpaenh8NhiaqsShbYsWOHVNNhhx0mnfo111xTWVlpFXz44YcPOeSQQw899Lnnnkssq7W5hx56SGIuRWbOnPnee+917dq1RYsW999/v7Xwl19+2bdvX9miLCC78ddff1nzP/zwQ8lYmjVrdt1115188sm2/bLR/Px8kef000//6aefrJlxCUZW8Wzq1Kk7d+58+umn5Zirq6tlvhxhmzZtVq5c+ccff5x//vlWxxlXVpmoS88qG0pLS3v++edlQ1JVEvTrr79eKkCiIFVonU9l/StWrBALpY6lSiSaMvPbb7+VCps/f74ETmpL9tZa4eOPP37CCSds2LBBVjJy5MiLL75YZiYb+3DEre7du991110yLYoMHDhQWosIJFKKCosWLZLDlEYoy8vuyZ5LY3vs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)

</center>
