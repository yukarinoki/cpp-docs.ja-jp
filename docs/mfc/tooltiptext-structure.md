---
title: TOOLTIPTEXT 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TOOLTIPTEXT
dev_langs:
- C++
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- tool tips [MFC], notifications
ms.assetid: 547591bf-80f5-400e-a2a7-0708cfffbb5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eeee8c7b0b3cd4977688b627cb27f73e39c7ea89
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437093"
---
# <a name="tooltiptext-structure"></a>TOOLTIPTEXT 構造体

書き込みで、[ツール ヒントの通知ハンドラー](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)を使用する必要がある、 **TOOLTIPTEXT**構造体。 メンバー、 **TOOLTIPTEXT**構造体には。

```cpp
typedef struct {
    NMHDR     hdr;        // required for all WM_NOTIFY messages
    LPTSTR    lpszText;   // see below
    TCHAR     szText[80]; // buffer for tool tip text
    HINSTANCE hinst;      // see below
    UINT      uflags;     // flag indicating how to interpret the
                          // idFrom member of the NMHDR structure
                          // that is included in the structure
} TOOLTIPTEXT, FAR *LPTOOLTIPTEXT;
```

*hdr*<br/>
テキストを必要とするツールを識別します。 必要に応じてこの構造体の唯一のメンバーは、コントロールのコマンド id です。 コントロールのコマンド ID になります、 *idFrom*のメンバー、 **NMHDR**構造体、構文を使用してアクセス`hdr.idFrom`します。 参照してください[NMHDR](/windows/desktop/api/richedit/ns-richedit-_nmhdr)のメンバーの詳細については、 **NMHDR**構造体。

*lpszText*<br/>
ツールは、テキストを受け取る文字列のアドレス。

*szText*<br/>
ツール ヒントのテキストを受け取るバッファー。 アプリケーションは、文字列のアドレスを指定する代わりに、このバッファーにテキストをコピーできます。

*hinst*<br/>
ツール ヒントのテキストとして使用する文字列を含むインスタンスのハンドル。 場合*lpszText*アドレスは、ツール ヒントのテキストのこのメンバーには NULL です。

処理するとき、`TTN_NEEDTEXT`通知メッセージで、次の方法のいずれかで表示される文字列を指定します。

- 指定されたバッファーにテキストをコピー、 *szText*メンバー。

- テキストを含むバッファーのアドレスをコピー、 *lpszText*メンバー。

- 文字列リソースの識別子をコピー、 *lpszText*メンバー、およびコピーするリソースを含むインスタンスのハンドル、 *hinst*メンバー。

## <a name="see-also"></a>関連項目

[CFrameWnd から派生していないウィンドウのツール ヒント](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

