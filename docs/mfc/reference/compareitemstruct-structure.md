---
title: COMPAREITEMSTRUCT 構造体
ms.date: 11/04/2016
f1_keywords:
- COMPAREITEMSTRUCT
helpviewer_keywords:
- COMPAREITEMSTRUCT structure [MFC]
ms.assetid: 4b7131a5-5c7d-4e98-aac7-e85650262b52
ms.openlocfilehash: 78a6e76ee3bbac5b32eb4bccf45578e63f763b75
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465417"
---
# <a name="compareitemstruct-structure"></a>COMPAREITEMSTRUCT 構造体

`COMPAREITEMSTRUCT`構造体は、識別子と並べ替えられた、オーナー描画リスト ボックスまたはコンボ ボックスの 2 つの項目のアプリケーションによって提供されるデータを提供します。

## <a name="syntax"></a>構文

```
typedef struct tagCOMPAREITEMSTRUCT {
    UINT CtlType;
    UINT CtlID;
    HWND hwndItem;
    UINT itemID1;
    DWORD itemData1;
    UINT itemID2;
    DWORD itemData2;
} COMPAREITEMSTRUCT;
```

#### <a name="parameters"></a>パラメーター

*CtlType*<br/>
(これは、オーナー描画リスト ボックスを指定します) ODT_LISTBOX または ODT_COMBOBOX (元のオーナー描画のコンボ ボックスを指定)。

*CtlID*<br/>
リスト ボックスまたはコンボ ボックス コントロールの ID。

*hwndItem*<br/>
コントロールのウィンドウ ハンドル。

*itemID1*<br/>
リスト ボックスまたはコンボ ボックスの比較対象の最初の項目のインデックス。

*itemData1*<br/>
比較対象となる最初の項目のアプリケーションによって提供されるデータ。 この値は、コンボ ボックスまたはリスト ボックスに、項目を追加する呼び出しに渡されました。

*itemID2*<br/>
リスト ボックスまたはコンボ ボックスの比較対象となる 2 番目の項目のインデックス。

*itemData2*<br/>
比較対象となる 2 番目の項目のアプリケーションによって提供されるデータ。 この値は、コンボ ボックスまたはリスト ボックスに、項目を追加する呼び出しに渡されました。

## <a name="remarks"></a>Remarks

アプリケーションでは、オーナー描画リスト ボックスまたは CBS_SORT または LBS_SORT スタイルで作成したコンボ ボックスに新しい項目を追加するたびに Windows は WM_COMPAREITEM メッセージ、所有者を送信します。 *LParam*メッセージのパラメーターにはへの long ポインターが含まれています、`COMPAREITEMSTRUCT`構造体。 メッセージを受信するとは、所有者は、2 つの項目を比較し、前に、その他のどの項目が並べ替えを示す値を返します。

## <a name="requirements"></a>必要条件

**ヘッダー:** winuser.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)

