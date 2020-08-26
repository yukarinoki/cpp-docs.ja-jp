---
title: rdx (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.rdx
helpviewer_keywords:
- rdx attribute
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
ms.openlocfilehash: f61eaf535102c8885e828176434acf221dfe2457
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836882"
---
# <a name="rdx"></a>rdx

レジストリキーを作成するか、既存のレジストリキーを変更します。

## <a name="syntax"></a>構文

```cpp
[ rdx(key, valuename=NULL, regtype) ]
```

### <a name="parameters"></a>パラメーター

*key*<br/>
作成または開くキーの名前。

*valuename*<br/>
Optional設定する値フィールドを指定します。 この名前の値フィールドがキーにまだ存在しない場合は、追加されます。

*regtype*<br/>
追加するレジストリキーの種類。 、、 `text` `dword` `binary` 、またはのいずれかを指定できます `CString` 。

## <a name="remarks"></a>解説

**Rdx** C++ 属性は、COM コンポーネントの既存のレジストリキーを作成または変更します。 属性は、ターゲットメンバーを実装するオブジェクトに BEGIN_RDX_MAP マクロを追加します。 `RegistryDataExchange`BEGIN_RDX_MAP マクロの結果として挿入された関数を使用して、レジストリとデータメンバーの間でデータを転送できます。

この属性は、 [コクラス](coclass.md)、 [progid](progid.md)、または [vi_progid](vi-progid.md) 属性、またはこれらの属性のいずれかを意味するその他の属性と組み合わせて使用できます。

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**`class`** または **`struct`** メンバー|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="example"></a>例

次のコードでは、CMyClass COM コンポーネントを記述するシステムに MyValue というレジストリキーを追加します。

```cpp
// cpp_attr_ref_rdx.cpp
// compile with: /LD /link /OPT:NOREF
#define _ATL_ATTRIBUTES
#include "atlbase.h"

[module (name="MyLib")];

class CMyClass {
public:
   CMyClass() {
      strcpy_s(m_sz, "SomeValue");
   }

   [ rdx(key = "HKCR\\MyApp.MyApp.1", valuename = "MyValue", regtype = "text")]
   char m_sz[256];
};
```

## <a name="see-also"></a>関連項目

[COM 属性](com-attributes.md)<br/>
[registration_script](registration-script.md)
