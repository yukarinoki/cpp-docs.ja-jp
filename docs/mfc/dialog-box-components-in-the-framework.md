---
title: フレームワークのダイアログ ボックス コンポーネント
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], creating
- dialog classes [MFC], dialog box components
- MFC dialog boxes [MFC], about MFC dialog boxes
- dialog templates [MFC], MFC framework
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
ms.openlocfilehash: b3290107337f60854e6abbd2f744aaa38af0b741
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616917"
---
# <a name="dialog-box-components-in-the-framework"></a>フレームワークのダイアログ ボックス コンポーネント

MFC フレームワークのダイアログボックスには、次の2つのコンポーネントがあります。

- ダイアログボックスのコントロールとその配置を指定するダイアログテンプレートリソース。

   ダイアログリソースには、Windows によってダイアログウィンドウが作成されて表示されるダイアログテンプレートが格納されます。 このテンプレートでは、ダイアログボックスのサイズ、位置、スタイル、ダイアログボックスのコントロールの種類と位置など、ダイアログボックスの特性を指定します。 通常は、リソースとして格納されているダイアログテンプレートを使用しますが、独自のテンプレートをメモリに作成することもできます。

- ダイアログボックスを管理するためのプログラムインターフェイスを提供するための、 [CDialog](reference/cdialog-class.md)から派生したダイアログクラス。

   ダイアログボックスはウィンドウであり、表示されると Windows のウィンドウに追加されます。 ダイアログウィンドウが作成されると、ダイアログボックスの子ウィンドウコントロールを作成するためのテンプレートとして、ダイアログテンプレートリソースが使用されます。

## <a name="see-also"></a>関連項目

[ダイアログボックス](dialog-boxes.md)<br/>
[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)
