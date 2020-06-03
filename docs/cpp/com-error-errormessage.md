---
title: _com_error::ErrorMessage
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorMessage
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
ms.openlocfilehash: b5e884956b5a51d3c714f1a81dc6945409f74f4b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180668"
---
# <a name="_com_errorerrormessage"></a>_com_error::ErrorMessage

**Microsoft 固有の仕様**

`_com_error` オブジェクトに格納された HRESULT の文字列メッセージを取得します。

## <a name="syntax"></a>構文

```
const TCHAR * ErrorMessage( ) const throw( );
```

## <a name="return-value"></a>戻り値

`_com_error` オブジェクト内に記録された HRESULT の文字列メッセージを返します。 HRESULT が、マップされた16ビット[Wcode](../cpp/com-error-wcode.md)の場合は、汎用メッセージ "`IDispatch error #<wCode>`" が返されます。 メッセージがない場合、一般的なメッセージ "`Unknown error #<hresult>`" が返されます。 返される文字列は _UNICODE マクロの状態によって、Unicode 文字列またはマルチバイト文字列です。

## <a name="remarks"></a>解説

`_com_error` オブジェクト内に記録された HRESULT の適切なシステムメッセージテキストを取得します。 システムメッセージテキストは、Win32 [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage)関数を呼び出すことによって取得されます。 返される文字列は `FormatMessage` API によって割り当てられ、`_com_error` オブジェクトが破棄されるときに解放されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_error クラス](../cpp/com-error-class.md)
