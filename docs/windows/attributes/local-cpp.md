---
description: '詳細情報: ローカル (C++)'
title: local (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.local
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
ms.openlocfilehash: 7fa1366b78576224f8fcc0d91392fe1fc6cb8af9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327512"
---
# <a name="local-c"></a>local (C++)

インターフェイスヘッダーで使用すると、MIDL コンパイラをヘッダージェネレーターとして使用できるようになります。 個々の関数で使用する場合は、スタブが生成されないローカルプロシージャを指定します。

## <a name="syntax"></a>構文

```cpp
[local]
```

## <a name="remarks"></a>解説

**ローカル** C++ 属性には、[ローカル](/windows/win32/Midl/local)の MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**ローカル** の使用方法の例については、「 [call_as](call-as.md) 」を参照してください。

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**インターフェイス**、インターフェイスメソッド|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|`dispinterface`|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[call_as](call-as.md)
