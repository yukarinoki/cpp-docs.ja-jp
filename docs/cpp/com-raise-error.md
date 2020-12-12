---
description: '詳細については、次を参照してください: _com_raise_error'
title: _com_raise_error
ms.date: 11/04/2016
f1_keywords:
- _com_raise_error
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
ms.openlocfilehash: 81697b565104971d22da04a7b8b0e33a7f9255ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178213"
---
# <a name="_com_raise_error"></a>_com_raise_error

**Microsoft 固有の仕様**

エラーへの応答として [_com_error](../cpp/com-error-class.md) をスローします。

## <a name="syntax"></a>構文

```cpp
void __stdcall _com_raise_error(
   HRESULT hr,
   IErrorInfo* perrinfo = 0
);
```

#### <a name="parameters"></a>パラメーター

*時間*<br/>
HRESULT 情報。

*perrinfo*<br/>
`IErrorInfo` オブジェクト。

## <a name="remarks"></a>解説

で定義されている **_com_raise_error** は、 \<comdef.h> 同じ名前およびプロトタイプのユーザーが記述したバージョンに置き換えることができます。 `#import` を使用し、C++ 例外処理を使用しない場合は、こうすることができます。 この場合、 **_com_raise_error** のユーザーバージョンでは、を実行する `longjmp` か、メッセージボックスを表示して停止することがあります。 ユーザー バージョンで返すことはできません。コンパイラ COM サポート コードがそれを予期していないためです。

[_Set_com_error_handler](../cpp/set-com-error-handler.md)を使用して、既定のエラー処理関数を置き換えることもできます。

既定では、 **_com_raise_error** は次のように定義されます。

```cpp
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {
   throw _com_error(hr, perrinfo);
}
```

**Microsoft 固有の仕様はここまで**

## <a name="requirements"></a>要件

**ヘッダー:**\<comdef.h>

**Lib:****Wchar_t がネイティブ型** のコンパイラオプションである場合は、comsuppw または comsuppw を使用します。 **Wchar_t がネイティブ型** である場合は、comsupp .lib を使用します。 詳細については、「 [/zc: wchar_t (Wchar_t はネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ COM グローバル関数](../cpp/compiler-com-global-functions.md)<br/>
[_set_com_error_handler](../cpp/set-com-error-handler.md)
