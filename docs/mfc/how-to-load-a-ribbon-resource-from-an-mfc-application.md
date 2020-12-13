---
description: '詳細については、「方法: MFC アプリケーションからリボンリソースを読み込む」を参照してください。'
title: '方法: MFC アプリケーションからリボン リソースを読み込む'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
ms.openlocfilehash: 231acbd475bf84b2623eb44f9a3500ab94145d06
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330193"
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
