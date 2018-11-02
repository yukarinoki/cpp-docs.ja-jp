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
ms.openlocfilehash: cf01e7b881b8f5c9c5ba9847ccf4e15dee3e18d9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518587"
---
# <a name="dialog-box-components-in-the-framework"></a>フレームワークのダイアログ ボックス コンポーネント

MFC フレームワークでは、ダイアログ ボックスは 2 つのコンポーネントがあります。

- ダイアログ ボックスのコントロールとその配置を指定するダイアログ テンプレート リソースです。

   ダイアログ リソースでは、元の Windows がダイアログ ウィンドウを作成し、表示するダイアログ テンプレートを格納します。 テンプレートには、サイズ、場所、スタイル、種類、ダイアログ ボックスのコントロールの位置など、ダイアログ ボックスの特性を指定します。 リソースとして格納されているダイアログ テンプレートを使用することは、通常は、メモリ内で、独自のテンプレートを作成することもできます。

- ダイアログ クラスから派生した[CDialog](../mfc/reference/cdialog-class.md)、ダイアログ ボックスを管理するためのプログラム インターフェイスを提供します。

   ダイアログ ボックスでは、ウィンドウし、表示される場合は、Windows ウィンドウにアタッチされます。 ダイアログ ウィンドウが作成されたときにダイアログ テンプレート リソースは、ダイアログ ボックスのウィンドウ コントロールの子を作成するため、テンプレートとして使用されます。

## <a name="see-also"></a>関連項目

[ダイアログ ボックス](../mfc/dialog-boxes.md)<br/>
[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

