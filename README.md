# 利用するリンク集

- Azure Portal: https://portal.azure.com
- Node.js のダウンロード: https://nodejs.org/en/ 
- Google Chrome のダウンロード: https://www.google.co.jp/chrome/
- Azure Communication Services のサンプルリポジトリ: https://github.com/Azure-Samples/communication-services-web-calling-hero.git
- Traffic Manager の検証で利用する HTML ファイル: https://github.com/tenjoufire-lab/CPaaSDemo/blob/main/SorryPage.html


- 画像1: https://katsujimemail.blob.core.windows.net/hol/Microsoft_logo_(2012).svg
- fluentui アイコン集： https://fluentsite.z22.web.core.windows.net/0.51.3/components/svg-icon/definition


画像を追加する際に追加するべきコード
Header.styles.ts

export const imgStyle = mergeStyles({
    width: '12rem',
    height: '4rem',
    selectors: {
        '@media (max-width: 67.1875rem)': {
            display: 'none'
        }
    }
});

Header.tsx
1. fluentui 要素のインポート
import { Separator, Pivot, PivotItem, Stack, Image, IImageStyles } from '@fluentui/react';

2. 画像インポート
import msLogoSVG from 'assets/Microsoft_logo_(2012).svg';

3. スタイルのインポート
import {
    headerContainer,
    pivotItemStyles,
    separatorContainerStyle,
    separatorStyles,
    pivotItemStyle,
    headerCenteredContainer,
    //追加
    imgStyle
} from './styles/Header.styles';

4. 画像の大きさを指定するコードの追加
const imageStyleProps: IImageStyles = {
    image: {
        height: '100%',
        width: '100%'
    },
    root: {}
};

5. 画像読み込み
const msLogoImageProps = { src: msLogoSVG.toString() };

6. 画像埋め込み
<Image
     alt="Microsoft Logo"
     className={imgStyle}
     styles={imageStyleProps}
     {...msLogoImageProps}
/>
