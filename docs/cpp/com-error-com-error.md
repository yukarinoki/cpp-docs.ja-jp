---
title: _com_error::_com_error
ms.date: 11/04/2016
f1_keywords:
- _com_error::_com_error
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
ms.openlocfilehash: 4ac902f0fda90f77526ef53139ef0d523d8c22e7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180785"
---
# <a name="_com_error_com_error"></a>_com_error::_com_error

**Microsoft 固有の仕様**

**_Com_error**オブジェクトを構築します。

## <a name="syntax"></a>構文

```
_com_error(
   HRESULT hr,
   IErrorInfo* perrinfo = NULL,
   bool fAddRef=false) throw( );

_com_error( const _com_error& that ) throw( );
```

#### <a name="parameters"></a>パラメーター

*hr*<br/>
HRESULT 情報。

*perrinfo*<br/>
`IErrorInfo` オブジェクト。

*fAddRef*<br/>
既定では、コンストラクターは null 以外の `IErrorInfo` インターフェイスで AddRef を呼び出します。 これは、次のように、インターフェイスの所有権が **_com_error**オブジェクトに渡される一般的なケースで、正しい参照カウントを提供します。

```cpp
throw _com_error(hr, perrinfo);
```

コードによって **_com_error**オブジェクトに所有権が譲渡されないようにし、 **_com_error**デストラクターで `Release` をオフセットするために `AddRef` が必要な場合は、次のようにオブジェクトを構築します。

```cpp
_com_error err(hr, perrinfo, true);
```

*それ*<br/>
既存の **_com_error**オブジェクト。

## <a name="remarks"></a>解説

最初のコンストラクターは、HRESULT およびオプションの `IErrorInfo` オブジェクトを指定して、新しいオブジェクトを作成します。 2番目の方法では、既存の **_com_error**オブジェクトのコピーを作成します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_error クラス](../cpp/com-error-class.md)
