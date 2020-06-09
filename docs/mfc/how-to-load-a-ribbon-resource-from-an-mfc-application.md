---
title: '方法: MFC アプリケーションからリボン リソースを読み込む'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
ms.openlocfilehash: 47a3b94bbcb14c6c2923524db1f6a83b687e50e8
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626408"
---
# <a name="how-to-load-a-ribbon-resource-from-an-mfc-application"></a>方法: MFC アプリケーションからリボン リソースを読み込む

アプリケーションでリボンリソースを使用するには、リボンリソースを読み込むようにアプリケーションを変更します。

### <a name="to-load-a-ribbon-resource"></a>リボンリソースを読み込むには

1. `Ribbon Control`クラスでオブジェクトを宣言し `CMainFrame` ます。

```
    CMFCRibbonBar m_wndRibbonBar;
```

1. で `CMainFrame::OnCreate` 、リボンコントロールを作成して初期化します。

```
    if (!m_wndRibbonBar.Create (this))
{
    return -1;
}

    if (!m_wndRibbonBar.LoadFromResource(IDR_RIBBON))
{
    return -1;
}
```

## <a name="see-also"></a>関連項目

[リボンデザイナー (MFC)](ribbon-designer-mfc.md)
