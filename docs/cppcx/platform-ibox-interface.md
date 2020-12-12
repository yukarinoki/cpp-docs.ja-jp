---
description: '詳細情報: Platform:: IBox インターフェイス'
title: Platform::IBox インターフェイス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
ms.assetid: 774df45d-f8a7-45a3-ae24-eecc3c681040
ms.openlocfilehash: abd1b9107fe1d472135f2b2addc7fa4b0f88ecfd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195178"
---
# <a name="platformibox-interface"></a>Platform::IBox インターフェイス

[Platform::IBox](../cppcx/platform-ibox-interface.md) のインターフェイスは `Windows::Foundation::IReference` のインターフェイスの C++ の名前です。

## <a name="syntax"></a>構文

```cpp
template <typename T>
interface class IBox
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
ボックス化された値の型。

### <a name="remarks"></a>解説

`IBox<T>` インターフェイスは、「 [値クラスと構造体 (C++/CX)](../cppcx/value-classes-and-structs-c-cx.md)」で説明されているように、主に内部的に使用され、null 許容値型を表します。 インターフェイスは、 `Object^`型のパラメーターを受け取る C++ のメソッドに渡される値の型をボックス化するためにも使用されます。 入力パラメーターは `IBox<SomeValueType>`として明示的に宣言できます。 例については、「 [ボックス](../cppcx/boxing-c-cx.md)化」を参照してください。

### <a name="requirements"></a>要件

### <a name="members"></a>メンバー

`Platform::IBox` インターフェイスは [Platform::IValueType](../cppcx/platform-ivaluetype-interface.md) インターフェイスから継承されます。 `IBox` には、次に示すメンバーがあります。

**プロパティ**

|Method|説明|
|------------|-----------------|
|[Value](#value)|以前にこの `IBox` インスタンスに格納されていたことがあり、ボックス化が解除されている値を返します。|

## <a name="iboxvalue-property"></a><a name="value"></a> IBox:: Value プロパティ

このオブジェクトに元から格納されていた値を返します。

### <a name="syntax"></a>構文

```cpp
property T Value {T get();}
```

### <a name="parameters"></a>パラメーター

*T*<br/>
ボックス化された値の型。

### <a name="property-valuereturn-value"></a>プロパティ値/戻り値

このオブジェクトに元から格納されていた値を返します。

### <a name="remarks"></a>解説

例については、「 [ボックス](../cppcx/boxing-c-cx.md)化」を参照してください。

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)
