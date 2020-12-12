---
description: '詳細情報: 次を参照してください。'
title: 方法 getlasterror (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.usesgetlasterror
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
ms.openlocfilehash: f43ae005e2f888f4318900cbde58f449011bd15e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329511"
---
# <a name="usesgetlasterror"></a>usesgetlasterror

この関数を呼び出したときにエラーが発生した場合に、呼び出し元がを呼び出してエラーコードを取得できることを呼び出し元に通知し `GetLastError` ます。

## <a name="syntax"></a>構文

```cpp
[usesgetlasterror]
```

## <a name="remarks"></a>解説

Has **getlasterror** C++ 属性に [は、すべて](/windows/win32/Midl/usesgetlasterror) の機能と同じ機能があります。

## <a name="example"></a>例

使用方法の例については、 [idl_module](idl-module.md)の例を **参照してください。**

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**module** 属性|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)
