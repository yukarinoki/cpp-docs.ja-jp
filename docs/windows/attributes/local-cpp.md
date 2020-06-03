---
title: local (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.local
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
ms.openlocfilehash: d3710eee748a43a1daa5c07d8b3feb6beb8f64fa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214748"
---
# <a name="local-c"></a>local (C++)

インターフェイスヘッダーで使用すると、MIDL コンパイラをヘッダージェネレーターとして使用できるようになります。 個々の関数で使用する場合は、スタブが生成されないローカルプロシージャを指定します。

## <a name="syntax"></a>構文

```cpp
[local]
```

## <a name="remarks"></a>解説

**ローカル** C++属性には、[ローカル](/windows/win32/Midl/local)の MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**ローカル**の使用方法の例については、「 [call_as](call-as.md) 」を参照してください。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**インターフェイス**、インターフェイスメソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|`dispinterface`|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[call_as](call-as.md)
