---
description: '詳細情報: CUserException クラス'
title: CUserException クラス
ms.date: 11/04/2016
f1_keywords:
- CUserException
helpviewer_keywords:
- operations [MFC], stopping
- exceptions [MFC], throwing
- CUserException class [MFC]
- errors [MFC], trapping
- operations [MFC]
- throwing exceptions [MFC], stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
ms.openlocfilehash: 6104aa2883a80f88aed03634f09ad1947e9c6794
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344966"
---
# <a name="cuserexception-class"></a>CUserException クラス

エンド ユーザーの操作を中止するためにスローします。

## <a name="syntax"></a>構文

```
class CUserException : public CSimpleException
```

## <a name="remarks"></a>解説

`CUserException`アプリケーション固有の例外に対して throw/catch 例外メカニズムを使用する場合は、を使用します。 クラス名の "user" は、"ユーザーが処理する必要がある何らかの例外が発生しました。" と解釈できます。

通常、は、 `CUserException` グローバル関数を呼び出した後に、 `AfxMessageBox` 操作が失敗したことをユーザーに通知するためにスローされます。 例外ハンドラーを記述する場合は、通常、ユーザーにエラーが通知されているため、例外を特別に処理します。 この例外は、フレームワークによってスローされます。 自分自身をスローするには `CUserException` 、ユーザーに警告し、グローバル関数を呼び出し `AfxThrowUserException` ます。

次の例では、失敗する可能性がある操作を含む関数は、ユーザーに警告し、をスローし `CUserException` ます。 呼び出し元の関数は、例外をキャッチし、それを特別に処理します。

[!code-cpp[NVC_MFCExceptions#24](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]

の使用方法の詳細については `CUserException` 、「 [例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CUserException`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CException クラス](../../mfc/reference/cexception-class.md)
