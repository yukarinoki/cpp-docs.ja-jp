---
description: '詳しくは、「方法: 既存の MFC リボンをリボンリソースに変換する」をご覧ください。'
title: '方法: 既存の MFC リボンをリボン リソースに変換する'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource, converting from an MFC ribbon
- MFC ribbon, converting to a ribbon resource
ms.assetid: 324b7ff6-58f9-4691-96a9-9836a79d0fb6
ms.openlocfilehash: 825b8b4e3322afd8919ffad0f5e0f73c9d52be78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290285"
---
# <a name="how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource"></a>方法: 既存の MFC リボンをリボン リソースに変換する

リボンリソースは、手動でコード化されたリボンよりも視覚化、変更、および保守が簡単です。 このトピックでは、MFC プロジェクトの手動でコード化されたリボンをリボンリソースに変換する方法について説明します。

MFC リボンクラス ( [CMFCRibbonBar クラス](reference/cmfcribbonbar-class.md)など) を使用するコードを含む既存の mfc プロジェクトが必要です。

### <a name="to-convert-an-mfc-ribbon-to-a-ribbon-resource"></a>MFC リボンをリボンリソースに変換するには

1. Visual Studio の既存の MFC プロジェクトで、 `CMFCRibbonBar` オブジェクトが初期化されているソースファイルを開きます。 通常、このファイルは mainfrm.cpp です。 リボンの初期化コードの後に、次のコードを追加します。

```
    m_wndRibbonBar.SaveToXMLFile("RibbonOutput.xml");
```

   ファイルを保存して閉じます。

1. MFC アプリケーションをビルドして実行し、メモ帳で RibbonOutput.txt を開き、その内容をコピーします。

1. Visual Studio の [ **プロジェクト** ] メニューで、[ **リソースの追加**] をクリックします。 [ **リソースの追加** ] ダイアログボックスで [ **リボン** ] を選択し、[ **新規作成**] をクリックします。

   Visual Studio によってリボンリソースが作成され、[デザイン] ビューで開きます。 リボンリソース ID は IDR_RIBBON1 であり、 **リソースビュー** に表示されます。 リボンは、ribbon1.vb XML ファイルで定義されています。

1. Visual Studio で、ribbon1.vb を開き、その内容を削除してから、先ほどコピーした RibbonOutput.txt の内容を貼り付けます。 Ribbon1.vb. .mfcribbon-ms-ms を保存して閉じます。

1. CMFCRibbonBar オブジェクトが初期化されているソースファイル (通常は mainfrm.cpp) を開き、既存のリボンコードをコメントアウトします。 コメントアウトしたコードの後に、次のコードを追加します。

```
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
```

1. プロジェクトをビルドし、プログラムを実行します。

## <a name="see-also"></a>関連項目

[リボンデザイナー (MFC)](ribbon-designer-mfc.md)
