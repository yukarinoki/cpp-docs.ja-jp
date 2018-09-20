---
title: SafeCast |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeCast
dev_langs:
- C++
helpviewer_keywords:
- SafeCast function
ms.assetid: 55316729-8456-403a-9f96-59d4038f67af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 65794dafe5e45cbd4c0e2a7eb49c34377009deee
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392984"
---
# <a name="safecast"></a>SafeCast

型の数値を別の型にキャストします。

## <a name="syntax"></a>構文

```cpp
template<typename T, typename U>
inline bool SafeCast (
   const T From,
   U& To
);
```

### <a name="parameters"></a>パラメーター

*From*<br/>
[in]変換するソースの数。 これは、型でなければなりません`T`します。

*目的*<br/>
[out]新しい数値型への参照。 これは、型でなければなりません`U`します。

## <a name="return-value"></a>戻り値

**true**場合、エラーは発生しません。**false**エラーが発生した場合。

## <a name="remarks"></a>Remarks

このメソッドの一部は、 [SafeInt ライブラリ](../windows/safeint-library.md)のインスタンスを作成せず、1 つのキャスト操作のものでは、 [SafeInt クラス](../windows/safeint-class.md)します。

> [!NOTE]
> このメソッドは、1 つの操作を保護する必要がありますにのみ使用する必要があります。 使用する必要があります複数の操作がある場合、`SafeInt`個々 のスタンドアロン関数の呼び出しではなくクラス。

T および U のテンプレートの種類の詳細については、次を参照してください。 [SafeInt 関数](../windows/safeint-functions.md)します。

## <a name="requirements"></a>要件

**ヘッダー:** safeint.h

**Namespace:** Microsoft::Utilities

## <a name="see-also"></a>関連項目

[SafeInt 関数](../windows/safeint-functions.md)<br/>
[SafeInt ライブラリ](../windows/safeint-library.md)<br/>
[SafeInt クラス](../windows/safeint-class.md)