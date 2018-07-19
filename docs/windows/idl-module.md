---
title: idl_module |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.idl_module
dev_langs:
- C++
helpviewer_keywords:
- idl_module attribute
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 11547a3fb1bd46a1e2edb8ce9dd0a6547464f796
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882525"
---
# <a name="idlmodule"></a>idl_module
.Dll ファイルにエントリ ポイントを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ idl_module (   
   name=module_name,   
   dllname=dll,   
   uuid="uuid",   
   helpstring="help text",   
   helpstringcontext=helpcontextID,   
   helpcontext=helpcontext,   
   hidden,   
   restricted  
) ]  
function declaration  
```  
  
#### <a name="parameters"></a>パラメーター  
 **name**  
 .Idl ファイル内に表示されるコード ブロックのユーザー定義の名前。  
  
 **dllname** (省略可能)  
 エクスポートを含む .dll ファイル。  
  
 `uuid` (省略可能)  
 一意の ID。  
  
 **helpstring** (省略可能)  
 タイプ ライブラリを記述するために使用する文字の文字列。  
  
 **helpstringcontext** (省略可能)  
 .Hlp や .chm ファイル内のヘルプ トピックの ID。  
  
 **helpcontext** (省略可能)  
 このタイプ ライブラリのヘルプ ID です。  
  
 **hidden** (省略可能)  
 ライブラリが表示されないようにするパラメーター。 詳細については、「 [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861) 」の MIDL 属性に関する説明を参照してください。  
  
 ***制限付き***(省略可能)  
 ライブラリのメンバーを任意に呼び出すことができません。 詳細については、「 [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157) 」の MIDL 属性に関する説明を参照してください。  
  
 *関数の宣言*  
 定義する関数。  
  
## <a name="remarks"></a>コメント  
 `idl_module` C++ 属性を使用して、.dll ファイルからインポートすることができる .dll ファイルにエントリ ポイントを指定できます。  
  
 **Idl_module**属性は、機能に似ていますが、[モジュール](http://msdn.microsoft.com/library/windows/desktop/aa367099)MIDL 属性。  
  
 .Idl ファイルのライブラリ ブロックに DLL エントリ ポイントを配置することにより、.dll ファイルからエクスポートできる COM オブジェクトから何もエクスポートできます。  
  
 使用する必要があります`idl_module`2 つの手順でします。 最初に、名前/DLL の組を定義する必要があります。 使用すると、`idl_module`エントリ ポイントを指定する名前と追加の属性を指定します。  
  
## <a name="example"></a>例  
 次のコードを使用する方法を示しています、`idl_module`属性。  
  
```  
// cpp_attr_ref_idl_module.cpp  
// compile with: /LD  
[idl_quote("midl_pragma warning(disable:2461)")];  
[module(name="MyLibrary"), idl_module(name="MyLib", dllname="xxx.dll")];  
[idl_module(name="MyLib"), entry(4), usesgetlasterror]  
void FuncName(int i);  
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
 [entry](../windows/entry.md)   
