---
title: progid |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.progid
dev_langs:
- C++
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f2b2d2168b568c74c5404cc83bab1e5f77570773
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880434"
---
# <a name="progid"></a>progid
COM オブジェクトの ProgID を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ progid(  
   name  
) ];  
```  
  
#### <a name="parameters"></a>パラメーター  
 *name*  
 オブジェクトを表す ProgID です。  
  
 Progid は、COM/ActiveX オブジェクトを識別するために使用したクラス id (CLSID) の人間が判読できるバージョンを表示します。  
  
## <a name="remarks"></a>コメント  
 **Progid** C++ 属性では、COM オブジェクトの ProgID を指定することができます。 ProgID がフォーム*name1.name2.version*です。 指定しない場合、*バージョン*ProgID、既定のバージョンは 1 です。 指定しない場合*name1.name2*、既定の名前は*classname.classname*です。 指定しない場合**progid**を指定**vi_progid**、 *name1.name2*から取得した**vi_progid**と (次シーケンシャル数) のバージョンが追加されます。  
  
 属性ブロックを使用する場合**progid**も使用しません`uuid`、コンパイラでチェックするかどうかをレジストリ、 `uuid` 、指定された存在**progid**です。 場合**progid**が指定されていないバージョン (コクラス名前と、コクラスを作成する場合) の生成に使用される、 **progid**です。  
  
 **progid**意味、**コクラス**を指定する場合は、属性**progid**を指定することと同じですが、**コクラス**と**progid**属性。  
  
 **Progid**属性により指定された名前に自動的に登録するクラスが発生します。 生成された .idl ファイルは表示されません、 **progid**値。  
  
 ATL を使用するプロジェクト内でこの属性を使用する場合、属性の動作を変更します。 この属性で指定された情報を使用する上記の動作だけでなく、 **GetProgID**によって挿入された、関数、**コクラス**属性。 詳細については、次を参照してください。、[コクラス](../windows/coclass.md)属性。  
  
## <a name="example"></a>例  
 例を参照して[コクラス](../windows/coclass.md)の使用例の**progid**です。  
  
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
 [クラス属性](../windows/class-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [ProgID キー](http://msdn.microsoft.com/library/windows/desktop/dd542719)   
