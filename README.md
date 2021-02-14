# logo
Deutsch lernen

- 在自己的项目中，点上方 Actions 选项卡进入项目 GitHub Actions 页面, 点击绿色按钮 “I understand my workflows, go ahead and enable them” 开启自动提交功能


      - name: download
        run: |
          sudo apt-get update
          sudo apt-get install ffmpeg
          curl https://downloadzdf-a.akamaihd.net/mp4/zdf/21/02/210212_fr_neu_lot/2/210212_fr_neu_lot_3328k_p15v15.mp4 -o test.mp4
          
          git remote set-url origin https://${{ github.actor }}:${{ secrets.GITHUB_TOKEN }}@github.com/${{ github.repository }}
          git pull --rebase
