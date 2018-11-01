---
title: DEVNAMES 構造体
ms.date: 11/04/2016
f1_keywords:
- DEVNAMES
helpviewer_keywords:
- DEVNAMES [MFC]
ms.assetid: aac97f60-2169-471a-ba5d-c0baed9eed9a
ms.openlocfilehash: 1fe553401ccf7a054ba7a19642aca2882bfa8fac
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441973"
---
# <a name="devnames-structure"></a>DEVNAMES 構造体

`DEVNAMES`構造体には、ドライバー、デバイス、およびプリンターの出力ポート名を識別する文字列が含まれています。

## <a name="syntax"></a>構文

```
typedef struct tagDEVNAMES { /* dvnm */
    WORD wDriverOffset;
    WORD wDeviceOffset;
    WORD wOutputOffset;
    WORD wDefault; */* driver,
    device,
    and port-name strings follow wDefault */
} DEVNAMES;
```

#### <a name="parameters"></a>パラメーター

*wDriverOffset*<br/>
(入力/出力)デバイス ドライバーのファイル名 (拡張子なし) を含む null で終わる文字列の文字オフセットを指定します。 入力でこの文字列を使用して、ダイアログ ボックスで最初に表示するプリンターを決めます。

*wDeviceOffset*<br/>
(入力/出力)デバイスの名前を含む null で終わる文字列 (最大 32 バイトが、null を含む) への文字オフセットを指定します。 この文字列と同じである必要があります、`dmDeviceName`のメンバー、 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea)構造体。

*wOutputOffset*<br/>
(入力/出力)出力の物理メディア (出力ポート) の DOS デバイス名を含む null で終わる文字列の文字オフセットを指定します。

*時*<br/>
文字列が含まれるかどうかを指定します、`DEVNAMES`構造体は、既定のプリンターを識別します。 この文字列を使用して、最後の印刷操作の既定のプリンターが変更されていないことを確認します。 、入力時のフラグが設定されている場合、他の値で、`DEVNAMES`構造体が現在の既定のプリンターに対してチェックされます。 文字列が一致しない場合、ドキュメントを再フォーマットする必要があるユーザーに知らせる警告メッセージが表示されます。 出力では、`wDefault`メンバーが変更されるは、印刷のセットアップ ダイアログ ボックスが表示され、ユーザーが ok ボタンを選択した場合にのみです。 既定のプリンターを選択した場合、時フラグが設定されます。 特定のプリンターを選択すると、フラグが設定されていません。 このメンバーの他のすべてのビットは、[印刷] ダイアログ ボックス プロシージャによって内部使用のために予約されています。

## <a name="remarks"></a>Remarks

`PrintDlg`関数では、これらの文字列を使用して、システム定義の印刷 ダイアログ ボックスでメンバーを初期化します。 ユーザーは、ダイアログ ボックスを閉じ、この構造体で、選択したプリンターに関する情報が返されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** commdlg.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CPrintDialog::CreatePrinterDC](../../mfc/reference/cprintdialog-class.md#createprinterdc)

