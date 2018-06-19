---
title: DEVNAMES 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DEVNAMES
dev_langs:
- C++
helpviewer_keywords:
- DEVNAMES [MFC]
ms.assetid: aac97f60-2169-471a-ba5d-c0baed9eed9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3234df2f0430ea75399791f4fd88a636a63b67e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371479"
---
# <a name="devnames-structure"></a>DEVNAMES 構造体
`DEVNAMES`構造には、ドライバー、デバイス、およびプリンターの出力ポート名を識別する文字列が含まれています。  
  
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
 *wDriverOffset*  
 (入力/出力)(拡張子なし)、デバイス ドライバーのファイル名を表す null で終わる文字列への文字数でオフセットを指定します。 入力時にこの文字列を使用して、ダイアログ ボックスに最初に表示するプリンターを決めます。  
  
 *wDeviceOffset*  
 (入力/出力)デバイスの名前を表す null で終わる文字列 (null を含む 32 バイトの最大値) に文字、オフセットを指定します。 この文字列と同じである必要があります、 **dmDeviceName**のメンバー、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)構造体。  
  
 *wOutputOffset*  
 (入力/出力)物理出力メディア (出力ポート) の DOS デバイス名を表す null で終わる文字列への文字数でオフセットを指定します。  
  
 *時*  
 文字列が含まれるかどうかを指定、`DEVNAMES`構造体は、既定のプリンターを識別します。 この文字列を使用して、既定のプリンターが最後の印刷操作の後に変更されていないことを確認してください。 入力、**時**フラグが設定されて、その他の値、`DEVNAMES`構造体は、現在の既定のプリンターに対してチェックされます。 文字列が一致しない場合、ドキュメントが再フォーマットする必要があるユーザーに知らせる警告メッセージが表示されます。 出力では、**時**メンバーが変更されるは、印刷のセットアップ ダイアログ ボックスが表示され、ユーザーが ok ボタンを選択した場合にのみです。 **時**通常使うプリンターを選択した場合、フラグが設定されています。 特定のプリンターを選択すると、フラグが設定されていません。 このメンバーの他のすべてのビットは、[印刷] ダイアログ ボックス プロシージャで内部使用のために予約されています。  
  
## <a name="remarks"></a>コメント  
 **PrintDlg**関数では、これらの文字列を使用して、システム定義の印刷 ダイアログ ボックスでメンバーを初期化します。 ユーザーは、ダイアログ ボックスを閉じ、この構造体で、選択したプリンターに関する情報が返されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** commdlg.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPrintDialog::CreatePrinterDC](../../mfc/reference/cprintdialog-class.md#createprinterdc)


