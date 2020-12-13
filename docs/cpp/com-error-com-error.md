---
description: '詳細については、「_com_error:: _com_error」を参照してください。'
title: _com_error::_com_error
ms.date: 11/04/2016
f1_keywords:
- _com_error::_com_error
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
ms.openlocfilehash: 2c5b912f5d532e9aed5b8e84a3fe7e2fcd7d4100
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332559"
---
# <a name="_com_error_com_error"></a>_com_error::_com_error

**Microsoft 固有の仕様**

**_Com_error** オブジェクトを構築します。

## <a name="syntax"></a>構文

```
_com_error(
   HRESULT hr,
   IErrorInfo* perrinfo = NULL,
   bool fAddRef=false) throw( );

_com_error( const _com_error& that ) throw( );
```

#### <a name="parameters"></a>パラメーター

*時間*<br/>
HRESULT 情報。

*perrinfo*<br/>
`IErrorInfo` オブジェクト。

*fAddRef*<br/>
既定では、コンストラクターは null 以外のインターフェイスで AddRef を呼び出し `IErrorInfo` ます。 これは、次のように、インターフェイスの所有権が **_com_error** オブジェクトに渡される一般的なケースで、正しい参照カウントを提供します。

```cpp
throw _com_error(hr, perrinfo);
```

コードによって **_com_error** オブジェクトに所有権を転送する必要がなく、 `AddRef` _com_error デストラクターでをオフセットする必要がある場合は、次のように `Release` オブジェクトを構築します。 

```cpp
_com_error err(hr, perrinfo, true);
```

*that*<br/>
既存の **_com_error** オブジェクト。

## <a name="remarks"></a>解説

最初のコンストラクターは、HRESULT とオプションのオブジェクトを指定して、新しいオブジェクトを作成し `IErrorInfo` ます。 2番目の方法では、既存の **_com_error** オブジェクトのコピーを作成します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)
