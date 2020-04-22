---
title: _com_raise_error
ms.date: 11/04/2016
f1_keywords:
- _com_raise_error
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
ms.openlocfilehash: f5efbe98a489a380c4e9be5a0e40603be2a409c0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745085"
---
# <a name="_com_raise_error"></a>_com_raise_error

**マイクロソフト固有**

エラーに対して[_com_error](../cpp/com-error-class.md)をスローします。

## <a name="syntax"></a>構文

```cpp
void __stdcall _com_raise_error(
   HRESULT hr,
   IErrorInfo* perrinfo = 0
);
```

#### <a name="parameters"></a>パラメーター

*人事*<br/>
HRESULT 情報。

*ペラーインフォ*<br/>
`IErrorInfo` オブジェクト。

## <a name="remarks"></a>解説

**_com_raise_error**は comdef.h>で\<定義され、同じ名前とプロトタイプのユーザー作成バージョンに置き換えることができます。 `#import` を使用し、C++ 例外処理を使用しない場合は、こうすることができます。 その場合、ユーザー バージョンの **_com_raise_error**が、 を`longjmp`実行するか、またはメッセージ ボックスを表示して停止する場合があります。 ユーザー バージョンで返すことはできません。コンパイラ COM サポート コードがそれを予期していないためです。

また[、_set_com_error_handler](../cpp/set-com-error-handler.md)を使用して、デフォルトのエラー処理関数を置き換えることもできます。

デフォルトでは **、_com_raise_error**は次のように定義されます。

```cpp
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {
   throw _com_error(hr, perrinfo);
}
```

**エンド マイクロソフト 固有**

## <a name="requirements"></a>必要条件

**ヘッダー:** \<comdef.h>

**リブ:****wchar_tがネイティブ型**コンパイラ オプションをオンにしている場合は、comsuppw.lib または comsuppwd.lib を使用します。 **wchar_tネイティブ型が**オフの場合は、comsupp.lib を使用します。 「[/Zc:wchar_t (wchar_t をネイティブ型として認識)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ COM のグローバル関数](../cpp/compiler-com-global-functions.md)<br/>
[_set_com_error_handler](../cpp/set-com-error-handler.md)
