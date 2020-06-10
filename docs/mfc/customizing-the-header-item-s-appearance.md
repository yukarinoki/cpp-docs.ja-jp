---
title: ヘッダー項目&#39;の外観のカスタマイズ
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], customization of items
- CHeaderCtrl class [MFC], customizing the items
- HDS_ styles
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
ms.openlocfilehash: 8bf1bdad6a0408746b50b6b0dcbecbce308f5ede
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617087"
---
# <a name="customizing-the-header-item39s-appearance"></a>ヘッダー項目&#39;の外観のカスタマイズ

最初にヘッダーコントロール ([CHeaderCtrl:: create](reference/cheaderctrl-class.md#create)) を作成するときに*dwStyle*パラメーターを設定することにより、ヘッダー項目またはヘッダーコントロール自体の外観と動作を定義できます。

設定できるスタイルのサンプルとその用途は次のとおりです。

- ヘッダー項目がプッシュボタンのように見えるようにするには、 **HDS_BUTTONS**スタイルを使用します。

   Microsoft Outlook で行ったように、特定の列によるデータの並べ替えなど、ヘッダー項目に対するマウスクリックに応じてアクションを実行する場合は、このスタイルを使用します。

- マウスカーソルが上に置かれたときに、ヘッダー項目に "ホットトラッキング" の外観を与えるには、 **HDS_HOTTRACK**スタイルを使用します。

   ホットトラッキングは、他のフラットバー内の項目の上にポインターが渡されると、3D アウトラインを表示します。

- ヘッダーコントロールを非表示にする必要があることを示すには、 **HDS_HIDDEN**スタイルを使用します。

   **HDS_HIDDEN**スタイルは、ヘッダーコントロールがビジュアルコントロールではなくデータコンテナーとして使用されることを示します。 このスタイルでは、コントロールが自動的に非表示になることはありませんが、の動作に影響し `CHeaderCtrl::Layout` ます。 構造体の*cy*メンバーで返される値は `WINDOWPOS` 0 になり、コントロールがユーザーに表示されないことを示します。

これらのプロパティの詳細については、「Windows SDK 内の[項目](/windows/win32/Controls/header-controls)」を参照してください。 ヘッダーコントロールへの項目の追加の詳細については、「[ヘッダーコントロールへの項目の追加](adding-items-to-the-header-control.md)」を参照してください。

## <a name="see-also"></a>関連項目

[CHeaderCtrl の使い方](using-cheaderctrl.md)<br/>
[制限](controls-mfc.md)
