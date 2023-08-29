<template>
  <div class="content">
    <dv-full-screen-container>
      <div class="header">
        <div style="flex: 0 1 30%">
          <dv-decoration-10 style="height: 5px" />
          <div class="header-time">2023-13-31 24:00:00 星期八</div>
        </div>
        <div style="flex: 0 1 40%; margin-top: 3px">
          <div style="display: flex">
            <dv-decoration-8 style="flex: 0 1 30%; height: 50px" />
            <div class="title">数据可视化</div>
            <dv-decoration-8
              :reverse="true"
              style="flex: 0 1 30%; height: 50px"
            />
          </div>
        </div>
        <div style="flex: 0 1 30%">
          <dv-decoration-10 style="height: 5px; transform: rotateY(180deg)" />
        </div>
      </div>
      <div class="body">
        <dv-border-box-12
          style="flex: 0 1 25%; margin-top: -30px; margin-left: 20px"
        >
          <div class="left-body">
            <div class="first">
              <div class="left-f-header">
                <div class="left-f-title">总工单</div>
                <dv-decoration-3 style="width: 70%" />
              </div>
              <div class="cut-line"></div>
              <div class="left-f-scroll">
                <dv-scroll-board
                  :config="config"
                  style="height: 100%; color: rgb(13, 141, 216)"
                />
              </div>
            </div>
            <div class="second">
              <div class="left-s-header">
                <div class="left-s-title">子工单</div>
                <dv-decoration-3 style="width: 70%" />
              </div>
              <div class="cut-line"></div>
              <div class="left-s-scroll">
                <dv-scroll-board
                  :config="config"
                  style="height: 100%; color: rgb(13, 141, 216)"
                />
              </div>
            </div>
            <div class="third">
              <div class="left-t-header">
                <div class="left-t-title">生产单元展示图</div>
                <dv-decoration-6 style="width: 50%" />
              </div>
              <div class="cut-line"></div>
              <div class="left-t-cap">
                <dv-capsule-chart :config="config1" style="height: 100%" />
              </div>
            </div>
          </div>
        </dv-border-box-12>
        <div class="center-body">
          <div class="center-first">
            <dv-flyline-chart-enhanced
              :config="config5"
              style="width: 100%; height: 100%"
            />
          </div>
          <dv-border-box-10 style="flex: 0 1 29%">
            <div class="center-second">
              <div class="center-s-header">
                <div class="center-s-title">总工单</div>
                <dv-decoration-3 style="width: 50%" />
              </div>
              <div class="cut-line"></div>
              <div class="center-s-scroll">
                <dv-scroll-board
                  :config="config"
                  style="height: 100%; color: rgb(13, 141, 216)"
                />
              </div>
            </div>
          </dv-border-box-10>
        </div>
        <dv-border-box-12
          style="flex: 0 1 25%; margin-top: -30px; margin-left: 20px"
        >
          <div class="right-body">
            <div class="first">
              <div class="right-f-header">
                <div class="right-f-title">产能TOP</div>
                <dv-decoration-3 style="width: 70%" />
              </div>
              <div class="cut-line"></div>
              <div class="right-f-scroll">
                <dv-conical-column-chart
                  :config="config2"
                  style="height: 100%"
                />
              </div>
            </div>
            <div class="second">
              <div class="right-s-header">
                <div class="right-s-title">库存物料展示</div>
                <dv-decoration-3 style="width: 70%" />
              </div>
              <div class="cut-line"></div>
              <div class="right-s-scroll">
                <dv-scroll-ranking-board
                  :config="config3"
                  style="height: 19vh"
                />
              </div>
            </div>
            <div class="third">
              <div class="right-t-header">
                <div class="right-t-title">单元生产比例</div>
                <dv-decoration-6 style="width: 50%" />
              </div>
              <div class="cut-line"></div>
              <div class="right-t-cap">
                <dv-active-ring-chart :config="config4" style="height: 100%" />
                <!-- <dv-capsule-chart
                  :config="config1"
                  style="height: 100%; text-align: left"
                /> -->
              </div>
            </div>
          </div>
        </dv-border-box-12>
      </div>
    </dv-full-screen-container>
  </div>
</template>

<script>
export default {
  name: "HomeView",
  data() {
    return {
      config: {
        header: ["处理内容", "处理单位", "督办期限"],
        data: [
          ["未安排值班", "xxx司法局", "2023/06/14"],
          ["未安排值班", "xxx司法局", "2023/06/14"],
          ["未安排值班", "xxx司法局", "2023/06/14"],
          ["未安排值班", "xxx司法局", "2023/06/14"],
          ["未安排值班", "xxx司法局", "2023/06/14"],
          ["未安排值班", "xxx司法局", "2023/06/14"],
          ["未安排值班", "xxx司法局", "2023/06/14"],
          ["未安排值班", "xxx司法局", "2023/06/14"],
        ],
        headerBGC: "rgb(0 31 171)",
        align: ["center", "center", "center"],
        oddRowBGC: "",
      },
      config1: {
        data: [
          {
            name: "南阳",
            value: 167,
          },
          {
            name: "周口",
            value: 123,
          },
          {
            name: "漯河",
            value: 98,
          },
          {
            name: "郑州",
            value: 75,
          },
          {
            name: "西峡",
            value: 66,
          },
        ],
        unit: "单位",
        showValue: true,
      },
      config2: {
        data: [
          {
            name: "周口",
            value: 55,
          },
          {
            name: "南阳",
            value: 120,
          },
          {
            name: "西峡",
            value: 71,
          },
          {
            name: "驻马店",
            value: 66,
          },
          {
            name: "新乡",
            value: 80,
          },
          {
            name: "信阳",
            value: 35,
          },
          {
            name: "漯河",
            value: 15,
          },
        ],
        img: [
          require("../assets/1st.png"),
          require("../assets/2st.png"),
          require("../assets/3st.png"),
          require("../assets/4st.png"),
          require("../assets/5st.png"),
          require("../assets/6st.png"),
          require("../assets/7st.png"),
        ],
        showValue: true,
      },
      config3: {
        data: [
          {
            name: "周口",
            value: 55,
          },
          {
            name: "南阳",
            value: 120,
          },
          {
            name: "西峡",
            value: 78,
          },
          {
            name: "驻马店",
            value: 66,
          },
          {
            name: "新乡",
            value: 80,
          },
          {
            name: "信阳",
            value: 45,
          },
          {
            name: "漯河",
            value: 29,
          },
        ],
        unit: "万元",
      },
      config4: {
        radius: "60%",
        activeRadius: "65%",
        data: [
          {
            name: "周口",
            value: 55,
          },
          {
            name: "南阳",
            value: 120,
          },
          {
            name: "西峡",
            value: 78,
          },
          {
            name: "驻马店",
            value: 66,
          },
          {
            name: "新乡",
            value: 80,
          },
        ],
        digitalFlopStyle: {
          fontSize: 20,
        },
        showOriginValue: true,
      },
      config5: {
        points: [
          {
            name: "郑州",
            coordinate: [0.48, 0.35],
            halo: {
              show: true,
            },
            icon: {
              src: require("../assets/mapCenterPoint.png"),
              width: 30,
              height: 30,
            },
            text: {
              show: false,
            },
          },
          {
            name: "新乡",
            coordinate: [0.52, 0.23],
          },
          {
            name: "焦作",
            coordinate: [0.43, 0.29],
          },
          {
            name: "开封",
            coordinate: [0.59, 0.35],
          },
          {
            name: "许昌",
            coordinate: [0.53, 0.47],
          },
          {
            name: "平顶山",
            coordinate: [0.45, 0.54],
          },
          {
            name: "洛阳",
            coordinate: [0.36, 0.38],
          },
          {
            name: "周口",
            coordinate: [0.62, 0.55],
          },
          {
            name: "漯河",
            coordinate: [0.56, 0.56],
          },
          {
            name: "南阳",
            coordinate: [0.37, 0.66],
          },
          {
            name: "信阳",
            coordinate: [0.55, 0.81],
          },
          {
            name: "驻马店",
            coordinate: [0.55, 0.67],
          },
          {
            name: "济源",
            coordinate: [0.37, 0.29],
          },
          {
            name: "三门峡",
            coordinate: [0.2, 0.36],
          },
          {
            name: "商丘",
            coordinate: [0.76, 0.41],
          },
          {
            name: "鹤壁",
            coordinate: [0.59, 0.18],
          },
          {
            name: "濮阳",
            coordinate: [0.68, 0.17],
          },
          {
            name: "安阳",
            coordinate: [0.59, 0.1],
          },
        ],
        lines: [
          {
            source: "新乡",
            target: "郑州",
          },
          {
            source: "焦作",
            target: "郑州",
          },
          {
            source: "开封",
            target: "郑州",
          },
          {
            source: "许昌",
            target: "郑州",
          },
          {
            source: "平顶山",
            target: "郑州",
          },
          {
            source: "洛阳",
            target: "郑州",
          },
          {
            source: "周口",
            target: "郑州",
          },
          {
            source: "漯河",
            target: "郑州",
          },
          {
            source: "南阳",
            target: "郑州",
          },
          {
            source: "信阳",
            target: "郑州",
          },
          {
            source: "驻马店",
            target: "郑州",
          },
          {
            source: "济源",
            target: "郑州",
          },
          {
            source: "三门峡",
            target: "郑州",
          },
          {
            source: "商丘",
            target: "郑州",
          },
          {
            source: "鹤壁",
            target: "郑州",
          },
          {
            source: "濮阳",
            target: "郑州",
          },
          {
            source: "安阳",
            target: "郑州",
          },
        ],
        icon: {
          show: true,
          src: require("../assets/mapPoint.png"),
        },
        text: {
          show: true,
        },
        k: 0.5,
        bgImgSrc: require("../assets/map.jpg"),
      },
    };
  },
};
</script>

<style lang="scss" scoped>
.content {
  width: 100%;
  height: 100vh;
  background: url("../assets/pageBg.png") no-repeat center center;
  background-size: cover;
}
.header {
  display: flex;
  justify-content: space-between;
  margin-top: 5px;
  height: 8vh;
  .header-time {
    color: rgb(13, 141, 216);
    text-align: left;
    line-height: 100%;
    margin-left: 5%;
  }
  .title {
    color: rgb(30, 212, 212);
    flex: 0 1 40%;
    text-align: center;
    font-weight: 800;
    font-size: 2em;
    line-height: 50px;
  }
}
.body {
  display: flex;
  justify-content: space-between;
  .left-body {
    display: flex;
    flex-direction: column;
    height: 92vh;
    .first {
      flex: 0 1 33%;
      position: relative;
      width: 85%;
      margin: auto;
      .left-f-header {
        // margin-top: 10px;
        display: flex;
        height: 17%;
        justify-content: space-between;
        align-items: center;
        .left-f-title {
          color: rgb(13, 141, 216);
          font-size: 1em;
          font-weight: 600;
        }
      }
      .cut-line {
        margin-top: 2%;
        border: rgb(13, 141, 216) solid 1px;
      }
      .left-f-scroll {
        margin-top: 5%;
        height: 75%;
      }
    }
    .second {
      flex: 0 1 33%;
      width: 85%;
      margin: auto;
      .left-s-header {
        padding-top: 10px;
        display: flex;
        height: 17%;
        justify-content: space-between;
        align-items: center;
        .left-s-title {
          color: rgb(13, 141, 216);
          font-size: 1em;
          font-weight: 600;
        }
      }
      .cut-line {
        margin-top: 2%;
        border: rgb(13, 141, 216) solid 1px;
      }
      .left-s-scroll {
        margin-top: 5%;
        height: 75%;
      }
    }
    .third {
      flex: 0 1 34%;
      width: 85%;
      margin: auto;
      .left-t-header {
        margin-top: 10px;
        display: flex;
        height: 17%;
        justify-content: space-between;
        align-items: center;
        .left-t-title {
          color: rgb(13, 141, 216);
          font-size: 1em;
          font-weight: 600;
        }
      }
      .cut-line {
        margin-top: 2%;
        border: rgb(13, 141, 216) solid 1px;
      }
      .left-t-cap {
        margin-top: 2%;
        height: 75%;
      }
    }
  }
  .center-body {
    display: flex;
    flex: 0 1 50%;
    margin-top: 1%;
    flex-direction: column;
    margin-left: 20px;
    .center-first {
      flex: 0 1 70%;
    }
    .center-second {
      width: 85%;
      margin: auto;
      .center-s-header {
        display: flex;
        height: 17%;
        justify-content: space-between;
        align-items: center;
        .center-s-title {
          color: rgb(13, 141, 216);
          font-size: 1em;
          font-weight: 600;
        }
      }
      .cut-line {
        margin-top: 1%;
        border: rgb(13, 141, 216) solid 1px;
      }
      .center-s-scroll {
        margin-top: 2%;
        height: 80%;
      }
    }
  }
  .right-body {
    display: flex;
    flex-direction: column;
    height: 92vh;
    .first {
      flex: 0 1 33%;
      position: relative;
      width: 85%;
      margin: auto;
      .right-f-header {
        // margin-top: 10px;
        display: flex;
        height: 17%;
        justify-content: space-between;
        align-items: center;
        .right-f-title {
          color: rgb(13, 141, 216);
          font-size: 1em;
          font-weight: 600;
        }
      }
      .cut-line {
        margin-top: 2%;
        border: rgb(13, 141, 216) solid 1px;
      }
      .right-f-scroll {
        margin-top: 5%;
        height: 75%;
        text-align: left !important;
      }
    }
    .second {
      flex: 0 1 33%;
      width: 85%;
      margin: auto;
      .right-s-header {
        padding-top: 10px;
        display: flex;
        height: 17%;
        justify-content: space-between;
        align-items: center;
        .right-s-title {
          color: rgb(13, 141, 216);
          font-size: 1em;
          font-weight: 600;
        }
      }
      .cut-line {
        margin-top: 2%;
        border: rgb(13, 141, 216) solid 1px;
      }
      .right-s-scroll {
        margin-top: 5%;
        height: 75%;
      }
    }
    .third {
      flex: 0 1 34%;
      width: 85%;
      margin: auto;
      .right-t-header {
        margin-top: 10px;
        display: flex;
        height: 17%;
        justify-content: space-between;
        align-items: center;
        .right-t-title {
          color: rgb(13, 141, 216);
          font-size: 1em;
          font-weight: 600;
        }
      }
      .cut-line {
        margin-top: 2%;
        border: rgb(13, 141, 216) solid 1px;
      }
      .right-t-cap {
        margin-top: 2%;
        height: 75%;
      }
    }
  }
}
</style>
