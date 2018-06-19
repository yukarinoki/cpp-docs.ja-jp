---
title: インポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.import
dev_langs:
- C++
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b371cd1094a49f8a629cb6f8e880fd1210670f91
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877268"
---
# <a name="import"></a>import
メイン IDL から参照する定義を含む .idl、.odl ファイル、またはヘッダーの別のファイルを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ import(  
   idl_file  
) ];  
```  
  
#### <a name="parameters"></a>パラメーター  
 `idl_file`  
 現在のプロジェクトのタイプ ライブラリにインポートする .idl ファイルの名前。  
  
## <a name="remarks"></a>コメント  
 **インポート**C++ 属性により、`#import`ステートメントを下に配置する、`import "docobj.idl"`生成された .idl ファイル内のステートメント。 **インポート**属性と同じ機能を持つ、[インポート](http://msdn.microsoft.com/library/windows/desktop/aa367047)MIDL 属性。  
  
 **インポート**属性は、プロジェクトによって生成される .idl ファイルに指定されたファイルを配置するだけ、**インポート**属性ではソース コードから指定したファイルにコンス トラクターを呼び出すことはできませんで、プロジェクトです。  プロジェクトのソース コードから指定したファイルにコンス トラクターを呼び出すには使用するか、 [#import](../preprocessor/hash-import-directive-cpp.md)と`embedded_idl`属性またはするには、.h ファイルを含めることができます、 `idl_file`.h ファイルが存在する場合は、します。  
  
## <a name="example"></a>例  
 コード例を次に示します。  
  
```  
// cpp_attr_ref_import.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[import(import.idl)];  
```  
  
 生成された .idl ファイルに次のコードを生成します。  
  
```  
import "docobj.idl";  
import "import.idl";  
  
[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]  
library MyLib {  
   importlib("stdole2.tlb");  
   importlib("olepro32.dll");  
...  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|任意の場所|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [スタンドアロン属性](../windows/stand-alone-attributes.md)   
 [importidl](../windows/importidl.md)   
 [importlib](../windows/importlib.md)   
 [含まれます](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
