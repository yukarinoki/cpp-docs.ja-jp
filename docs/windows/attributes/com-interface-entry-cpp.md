---
title: com_interface_entry (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.com_interface_entry
helpviewer_keywords:
- com_interface_entry attribute
ms.assetid: 10368f81-b99b-4a0f-ba4f-a142e6911a5c
ms.openlocfilehash: 06df146ea47428ee782da7a93c2da7097e110324
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215349"
---
# <a name="com_interface_entry-c"></a>com_interface_entry (C++)

ターゲットクラスの COM マップにインターフェイスエントリを追加します。

## <a name="syntax"></a>構文

```cpp
[ com_interface_entry(
  com_interface_entry) ]
```

### <a name="parameters"></a>パラメーター

*com_interface_entry*<br/>
エントリの実際のテキストを格納している文字列。 使用可能な値の一覧については、「 [COM_INTERFACE_ENTRY マクロ](../../atl/reference/com-interface-entry-macros.md)」を参照してください。

## <a name="remarks"></a>解説

**Com_interface_entry** C++ 属性は、対象オブジェクトの com インターフェイスマップに文字列の unabridged の内容を挿入します。 属性が対象オブジェクトに1回適用された場合、エントリは既存のインターフェイスマップの先頭に挿入されます。 属性が同じ対象オブジェクトに繰り返し適用される場合、エントリは、受信された順にインターフェイスマップの先頭に挿入されます。

この属性を使用するには、 [coclass](coclass.md)、 [progid](progid.md)、または [vi_progid](vi-progid.md) 属性 (または、これらのいずれかを意味する別の属性) も同じ要素に適用する必要があります。 いずれか 1 つの属性を使用すると、他の 2 つも自動的に適用されます。 たとえば、が適用されている場合、 `progid` `vi_progid` と `coclass` も適用されます。

**Com_interface_entry**の最初の使用方法では、インターフェイスマップの先頭に新しいインターフェイスが挿入されるため、次のいずれかの COM_INTERFACE_ENTRY 型である必要があります。

- COM_INTERFACE_ENTRY

- COM_INTERFACE_ENTRY_IID

- COM_INTERFACE_ENTRY2

- COM_INTERFACE_ENTRY2_IID

**Com_interface_entry**属性の使用法を追加すると、サポートされているすべての COM_INTERFACE_ENTRY 型を使用できます。

ATL では、インターフェイスマップの最初のエントリを id として使用するため、この制限が必要です `IUnknown` 。したがって、エントリは有効なインターフェイスである必要があります。 たとえば、次のコードサンプルは、インターフェイスマップの最初のエントリに実際の COM インターフェイスが指定されていないため、無効です。

```cpp
[ coclass, com_interface_entry =
    "COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"
]
   class CMyClass
   {
   };
```

## <a name="example"></a>例

次のコードでは、の既存の COM インターフェイスマップに2つのエントリを追加し `CMyBaseClass` ます。 1つ目は標準のインターフェイスで、2番目のインターフェイスはインターフェイスを非表示にし `IDebugTest` ます。

```cpp
// cpp_attr_ref_com_interface_entry.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name ="ldld")];

[ object,
  uuid("7dbebed3-d636-4917-af62-c767a720a5b9")]
__interface IDebugTest{};

[ object,
  uuid("2875ceac-f94b-4087-8e13-d13dc167fcfc")]
__interface IMyClass{};

[ coclass,
  com_interface_entry ("COM_INTERFACE_ENTRY (IMyClass)"),
  com_interface_entry ("COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"),
  uuid("b85f8626-e76e-4775-b6a0-4826a9e94af2")
]

class CMyClass: public IMyClass, public IDebugTest
{
};
```

結果の COM オブジェクトマップは次のように `CMyBaseClass` なります。

```cpp
BEGIN_COM_MAP(CMyClass)
    COM_INTERFACE_ENTRY (IMyClass)
    COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)
    COM_INTERFACE_ENTRY(IMyClass)
    COM_INTERFACE_ENTRY2(IDispatch, IMyClass)
    COM_INTERFACE_ENTRY(IDebugTest)
    COM_INTERFACE_ENTRY(IProvideClassInfo)
END_COM_MAP()
```

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**適用対象**|**`class`**, **`struct`**|
|**Repeatable**|はい|
|**必須属性**|、、またはが1つ以上あり `coclass` `progid` `vi_progid` ます。|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[COM 属性](com-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 属性](typedef-enum-union-and-struct-attributes.md)
