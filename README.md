.skt-loading {
    pointer-events: none; /* 加载中阻止事件 */
    .skeleton {
      position: relative;
      overflow: hidden;
      border: none !important;
      border-radius: 5px;
      background-color: transparent !important;
      background-image: none !important;
      &::after {
        content: '';
        position: absolute;
        left: 0;
        top: 0;
        z-index: 9;
        width: 100%;
        height: 100%;
        background-color: #EBF1F8;
        display: block;
      }
      
      /* 下面这部分都是自定义的，看需求修改 */
      &:not(.not-round)::after {
        border-radius: 4px;
      }
      &:not(.not-before)::before {
        position: absolute;
        top: 0;
        width: 30%;
        height: 100%;
        content: "";
        background: linear-gradient(to right,rgba(255,255,255,0) 0,
            rgba(255,255,255,.3) 50%,rgba(255,255,255,0) 100%);
        transform: skewX(-45deg);
        z-index: 99;
        animation: skeleton-ani 1s ease infinite;
        display: block;
      }
      &.badge {
        &::after {
          background-color: #F8FAFC;
        }
      }
    }
  }

  @keyframes skeleton-ani { /* 骨架屏动画 */
    from {
      left: -100%;
    }
    to {
      left: 150%;
    }
  }
