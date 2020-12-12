---
description: '詳細については、「_com_error:: ErrorMessage」を参照してください。'
title: _com_error::ErrorMessage
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorMessage
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
ms.openlocfilehash: e7f91882d55e629744df5f26f7dcc64df1dddb22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296005"
---
# <a name="_com_errorerrormessage"></a>_com_error::ErrorMessage

**Microsoft 固有の仕様**

`_com_error` オブジェクトに格納された HRESULT の文字列メッセージを取得します。

## <a name="syntax"></a>構文

```
const TCHAR * ErrorMessage( ) const throw( );
```

## <a name="return-value"></a>戻り値

オブジェクト内に記録された HRESULT の文字列メッセージを返し `_com_error` ます。 HRESULT が、マップされた16ビット [Wcode](../cpp/com-error-wcode.md)の場合は、一般的なメッセージ " `IDispatch error #<wCode>` " が返されます。 メッセージがない場合、一般的なメッセージ "`Unknown error #<hresult>`" が返されます。 返される文字列は _UNICODE マクロの状態によって、Unicode 文字列またはマルチバイト文字列です。

## <a name="remarks"></a>解説

オブジェクト内に記録された HRESULT の適切なシステムメッセージテキストを取得し `_com_error` ます。 システムメッセージテキストは、Win32 [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) 関数を呼び出すことによって取得されます。 返される文字列は `FormatMessage` API によって割り当てられ、`_com_error` オブジェクトが破棄されるときに解放されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)
