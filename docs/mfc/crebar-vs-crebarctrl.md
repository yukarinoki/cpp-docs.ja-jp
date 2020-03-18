---
title: CReBar と CReBarCtrl の比較
ms.date: 11/04/2016
helpviewer_keywords:
- CReBar class [MFC], vs. CReBarCtrl
- rebar controls [MFC], CReBarCtrl class [MFC]
- GetReBarCtrl class [MFC]
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
ms.openlocfilehash: 94f889be453a17a55357a260bd2a0c07037f6ded
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445287"
---
# <a name="crebar-vs-crebarctrl"></a>CReBar と CReBarCtrl の比較

MFC には、 [CReBar](../mfc/reference/crebar-class.md)と[crebarctrl](../mfc/reference/crebarctrl-class.md) (Windows コモンコントロール API をラップする) の2つのクラスが用意されています。 `CReBar` には、rebar コモンコントロールのすべての機能が用意されており、必要な一般的なコントロール設定と構造の多くがユーザーに対して処理されます。

`CReBarCtrl` は Win32 rebar コントロールのラッパークラスであるため、rebar を MFC アーキテクチャに統合する予定がない場合は、実装が簡単になる可能性があります。 `CReBarCtrl` を使用し、rebar を MFC アーキテクチャに統合する予定がある場合は、rebar コントロールの操作を MFC に伝えるために、さらに注意する必要があります。 この通信は難しくありません。ただし、`CReBar`を使用する場合は、不要な追加作業です。

Visual C++には、rebar コモンコントロールを利用する2つの方法が用意されています。

- `CReBar`を使用して rebar を作成し、次に[CReBar:: GetReBarCtrl](../mfc/reference/crebar-class.md#getrebarctrl)を呼び出して、`CReBarCtrl` メンバー関数へのアクセスを取得します。

    > [!NOTE]
    >  `CReBar::GetReBarCtrl` は、rebar オブジェクトの**this**ポインターをキャストするインラインメンバー関数です。 これは、実行時に関数呼び出しにオーバーヘッドがないことを意味します。

- [Crebarctrl](../mfc/reference/crebarctrl-class.md)のコンストラクターを使用して rebar を作成します。

どちらの方法でも、rebar コントロールのメンバー関数へのアクセス権が付与されます。 `CReBar::GetReBarCtrl`を呼び出すと、いずれかのメンバー関数を使用できるように、`CReBarCtrl` オブジェクトへの参照が返されます。 `CReBar`を使用した rebar の構築と作成の詳細については、「 [CReBar](../mfc/reference/crebar-class.md) 」を参照してください。

## <a name="see-also"></a>参照

[CReBarCtrl の使い方](../mfc/using-crebarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
