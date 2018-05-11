---
title: emitidl |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.emitidl
dev_langs:
- C++
helpviewer_keywords:
- emitidl attribute
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e4c66ba8c49a405f9fdd93b1652626ab47488a53
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="emitidl"></a>emitidl
すべての後続の IDL 属性が処理され、生成された .idl ファイル内に配置するかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```
[ emitidl(state, defaultimports=boolean) ];
```  
  
### <a name="parameters"></a>パラメーター  
*state*  
これらの使用可能な値のいずれかの: **true**、 **false**、**強制**、**制限**、**プッシュ**、または**pop**です。  
  
-   場合**true**、ソース コード ファイルで発生した任意の IDL カテゴリ属性が生成された .idl ファイルに配置されます。 これは、既定の設定**emitidl**です。  
  
-   場合**false**、ソース コード ファイルで発生した任意の IDL カテゴリ属性が生成された .idl ファイルに配置されていません。  
  
-   場合**制限**、IDL 属性なしで、ファイルにある、[モジュール](../windows/module-cpp.md)属性。 コンパイラは、.idl ファイルを生成できません。  
  
-   場合**強制**、後ろに続くオーバーライド**制限**属性は、ファイルを持つ必要、**モジュール**属性 IDL がある場合は、ファイルの属性です。  
  
-   **プッシュ**現在を保存できる**emitidl**内部へ設定**emitidl**スタック、および**pop**設定できます**emitidl**どのような値は、内部の上部に**emitidl**スタック。  
  
`defaultimports=`*ブール*\(省略可能)  
-   場合*ブール*は**true**docobj.idl が生成された .idl ファイルにインポートします。 また場合は、.idl ファイルと同じ名前、.h ファイル`#include`.h ファイルと同じディレクトリ内に、ソース コードが検出されたし、生成された .idl ファイルには、その .idl ファイルのインポート ステートメントが含まれています。  
  
-   場合*ブール*は**false**docobj.idl が生成された .idl ファイルにインポートされていません。 .Idl ファイルをインポートする必要があります明示的に[インポート](../windows/import.md)です。  
  
## <a name="remarks"></a>コメント  
後に、 **emitidl** C++ 属性がソース コード ファイルで発生した、IDL カテゴリの属性が生成された .idl ファイルに配置されます。 ある場合ありません**emitidl**属性に、ソース コード ファイル内の IDL 属性が生成された .idl ファイルに出力します。  
  
複数を設定することは**emitidl**ソース コード ファイル内の属性です。 場合`[emitidl(false)];`後ろに続くなしでファイルに見つかりました`[emitidl(true)];`、生成された .idl ファイルの属性は処理されません。  
  
コンパイラが、新しいファイルを検出するたびに**emitidl**に暗黙的に設定されている**true**です。  
  
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
[コンパイラ属性](../windows/compiler-attributes.md)   
[スタンドアロン属性](../windows/stand-alone-attributes.md)   
[属性のサンプル](http://msdn.microsoft.com/en-us/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)