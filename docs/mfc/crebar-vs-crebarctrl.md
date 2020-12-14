---
description: '詳細については、次を参照してください: CReBar と CReBarCtrl'
title: CReBar とCReBarCtrl の比較
ms.date: 11/04/2016
helpviewer_keywords:
- CReBar class [MFC], vs. CReBarCtrl
- rebar controls [MFC], CReBarCtrl class [MFC]
- GetReBarCtrl class [MFC]
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
ms.openlocfilehash: 5a8dfe7594448319b4eb872abfb7022841d4e5dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309434"
---
# <a name="crebar-vs-crebarctrl"></a>CReBar とCReBarCtrl の比較

MFC には、 [CReBar](reference/crebar-class.md) と [crebarctrl](reference/crebarctrl-class.md) (Windows コモンコントロール API をラップする) の2つのクラスが用意されています。 `CReBar` rebar コモンコントロールのすべての機能を提供し、必要な共通コントロール設定と構造体の多くを処理します。

`CReBarCtrl` は、Win32 rebar コントロールのラッパークラスであるため、rebar を MFC アーキテクチャに統合する予定がない場合は、実装が簡単になる可能性があります。 Rebar を使用して MFC アーキテクチャに統合する予定がある場合は `CReBarCtrl` 、さらに注意を払って、rebar コントロールの操作を mfc に伝える必要があります。 この通信は難しくありません。ただし、を使用する場合は、不要な追加作業です `CReBar` 。

Visual C++ には、rebar コモンコントロールを利用する2つの方法があります。

- を使用して rebar を作成 `CReBar` し、 [CReBar:: GetReBarCtrl](reference/crebar-class.md#getrebarctrl) を呼び出して、メンバー関数へのアクセスを取得し `CReBarCtrl` ます。

    > [!NOTE]
    >  `CReBar::GetReBarCtrl` は、 **`this`** rebar オブジェクトのポインターをキャストするインラインメンバー関数です。 これは、実行時に関数呼び出しにオーバーヘッドがないことを意味します。

- [Crebarctrl](reference/crebarctrl-class.md)のコンストラクターを使用して rebar を作成します。

どちらの方法でも、rebar コントロールのメンバー関数へのアクセス権が付与されます。 を呼び出すと `CReBar::GetReBarCtrl` 、 `CReBarCtrl` メンバー関数のいずれかを使用できるように、オブジェクトへの参照が返されます。 を使用した rebar の構築と作成の詳細については、「 [CReBar](reference/crebar-class.md) 」を参照してください `CReBar` 。

## <a name="see-also"></a>関連項目

[CReBarCtrl の使い方](using-crebarctrl.md)<br/>
[コントロール](controls-mfc.md)
