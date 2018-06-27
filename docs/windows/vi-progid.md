---
title: vi_progid |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.vi_progid
dev_langs:
- C++
helpviewer_keywords:
- vi_progid attribute
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 687a8a70d7f0a5381160a6515c80f6940cc0a434
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891286"
---
# <a name="viprogid"></a>vi_progid
ProgID のバージョンに依存しない形式を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ vi_progid(  
   name  
) ];  
```  
  
#### <a name="parameters"></a>パラメーター  
 *name*  
 オブジェクトを表すバージョン依存 ProgID です。  
  
 Progid は、COM/ActiveX オブジェクトを識別するために使用したクラス id (CLSID) の人間が判読できるバージョンを表示します。  
  
## <a name="remarks"></a>コメント  
 **Vi_progid** C++ 属性では、COM オブジェクトのバージョンに依存しないプログラム Id を指定することができます。 ProgID がフォーム*name1.name2.version*です。 バージョン依存 ProgID がありません、*バージョン*します。 両方を指定することは、 **progid**と**vi_progid**コクラスの属性です。 指定しない場合**vi_progid**では、バージョン依存 ProgID がで指定された値、 [progid](../windows/progid.md)属性。  
  
 **vi_progid**意味、**コクラス**を指定する場合は、属性**vi_progid**を指定することと同じですが、**コクラス**と**vi_progid**属性。  
  
 **Vi_progid**属性により指定された名前に自動的に登録するクラスが発生します。 生成された .idl ファイルでは、ProgID の値は表示されません。  
  
 ATL プロジェクトの場合、[コクラス](../windows/coclass.md)属性が指定されても、指定された ProgID が使用、 **GetVersionIndependentProgID**関数 (によって挿入された、**コクラス**属性の場合) です。  
  
## <a name="example"></a>例  
 参照してください、[コクラス](../windows/coclass.md)のサンプルの使用例**vi_progid**です。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、 `struct`|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
 [ProgID キー](http://msdn.microsoft.com/library/windows/desktop/dd542719)   
