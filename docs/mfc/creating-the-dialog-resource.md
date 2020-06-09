---
title: ダイアログ リソースの作成
ms.date: 11/04/2016
helpviewer_keywords:
- dialog resources
- MFC dialog boxes [MFC], creating
- dialog templates [MFC], creating dialog resource
- templates [MFC], creating
- resources [MFC], creating dialog boxes
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 0b83bd33-14d3-4611-8129-fccdae18053e
ms.openlocfilehash: efaef11cfdc036a201ced3357ca81b37a5dc29db
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619621"
---
# <a name="creating-the-dialog-resource"></a>ダイアログ リソースの作成

ダイアログ[ボックス](dialog-boxes.md)をデザインし、ダイアログリソースを作成するには、[ダイアログエディター](../windows/dialog-editor.md)を使用します。 ダイアログエディターでは、次のことができます。

- ダイアログボックスが表示されるときのサイズと位置を調整します。

- コントロールパレットからさまざまな種類のコントロールをドラッグし、ダイアログボックスで必要な位置にドロップします。

- ツールバーの配置ボタンを使用してコントロールを配置します。

- プログラムに表示される外観と動作をシミュレートして、ダイアログボックスをテストします。 テストモードでは、テキストボックスにテキストを入力したり、プッシュボタンをクリックしたりして、ダイアログボックスのコントロールを操作できます。

完了すると、ダイアログテンプレートリソースがアプリケーションのリソーススクリプトファイルに格納されます。 必要に応じて後で編集できます。 ダイアログリソースを作成および編集する方法の詳細については、「[ダイアログエディター](../windows/dialog-editor.md)のトピック」を参照してください。 この手法は、 [CFormView](reference/cformview-class.md)クラスおよび[CRecordView](reference/crecordview-class.md)クラスのダイアログテンプレートリソースを作成するためにも使用されます。

ダイアログボックスが表示されたら、「[コードウィザードを使用してダイアログクラスを作成](creating-a-dialog-class-with-code-wizards.md)する」で説明されているように、ダイアログクラスを作成し、メッセージをマップします。

## <a name="see-also"></a>関連項目

[ダイアログボックス](dialog-boxes.md)<br/>
[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)
