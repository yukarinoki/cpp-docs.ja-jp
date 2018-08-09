---
title: rdx |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.rdx
dev_langs:
- C++
helpviewer_keywords:
- rdx attribute
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 32dd702dd7d429c4437875a6aead86ae687dfb2b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011050"
---
# <a name="rdx"></a>rdx
レジストリ キーを作成または既存のレジストリ キーを変更します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
[ rdx(   
   key,   
   valuename=NULL,   
   regtype   
) ]  
```  
  
### <a name="parameters"></a>パラメーター  
 *key*  
 作成または開かれたキーの名前。  
  
 *valuename* (省略可能)  
 設定する値のフィールドを指定します。 キーにもこの名前の値のフィールドがまだ存在しない場合は、追加されます。  
  
 *regtype です。*  
 追加されるレジストリ キーの型。 次のいずれかを指定できます: `text`、 `dword`、 `binary`、または`CString`します。  
  
## <a name="remarks"></a>Remarks  
 **Rdx** C++ 属性を作成または既存の COM コンポーネントのレジストリ キーを変更します。 属性は、対象のメンバーを実装するオブジェクトに BEGIN_RDX_MAP マクロを追加します。 `RegistryDataExchange`、レジストリおよびデータ メンバーの間でデータを転送する、BEGIN_RDX_MAP マクロした結果、挿入関数を使用できます  
  
 この属性を組み合わせて使用することができます、[コクラス](../windows/coclass.md)、 [progid](../windows/progid.md)、または[vi_progid](../windows/vi-progid.md)属性または他の属性をこれらのいずれかを意味します。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**または**構造体**メンバー|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="example"></a>例  
 次のコードは、CMyClass COM コンポーネントを記述するシステム プロパティと呼ばれるレジストリ キーを追加します。  
  
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
 [COM 属性](../windows/com-attributes.md)   
 [registration_script](../windows/registration-script.md)   