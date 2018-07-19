---
title: ATL レジストラーおよび解析ツリー |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parse trees
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb5b132e5e55ab5336254acaf4d2d3ae25440697
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358832"
---
# <a name="understanding-parse-trees"></a>パース ツリーについて
各解析ツリーが、次の形式を持つ、レジストラー スクリプトでは、1 つまたは複数のパース ツリーを定義できます。  
  
```  
<root key>{<registry expression>}+  
```  
  
 それぞれの文字について以下に説明します。  
  
```  
<root key> ::= HKEY_CLASSES_ROOT | HKEY_CURRENT_USER |  
    HKEY_LOCAL_MACHINE | HKEY_USERS |  
    HKEY_PERFORMANCE_DATA | HKEY_DYN_DATA |  
    HKEY_CURRENT_CONFIG | HKCR | HKCU |  
    HKLM | HKU | HKPD | HKDD | HKCC  
<registry expression> ::= <Add Key> | <Delete Key>  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
 [<Key Value>][{<Add Key>}]  
<Delete Key> ::= Delete<Key Name>  
<Key Name> ::= '<AlphaNumeric>+'  
<AlphaNumeric> ::= any character not NULL, i.e. ASCII 0  
<Key Value> ::== <Key Type><Key Name>  
<Key Type> ::= s | d  
<Key Value> ::= '<AlphaNumeric>'  
```  
  
> [!NOTE]
> `HKEY_CLASSES_ROOT` および`HKCR`は等価です。`HKEY_CURRENT_USER`と`HKCU`は同等; などです。  
  
 複数のキーとサブキーに解析ツリーに追加、\<ルート キー >。 これにより、サブキーのハンドル開いたまま、パーサーのすべてのサブキーの解析が完了するまでです。 このアプローチは、次の例のように、一度に 1 つのキーで動作しているよりも効率的です。  
  
```  
HKEY_CLASSES_ROOT  
{  
 'MyVeryOwnKey'  
 {  
 'HasASubKey'  
 {  
 'PrettyCool'  
 }  
 }  
}  
```  
  
 ここでは、レジストラー初期状態が表示されます (作成)`HKEY_CLASSES_ROOT\MyVeryOwnKey`です。 確認し、`MyVeryOwnKey`サブキーがあります。 キーを閉じるのではなく`MyVeryOwnKey`、レジストラーが、ハンドルを保持し、開きます (作成)`HasASubKey`この親ハンドルを使用します。 (システム レジストリできます低速親ハンドルが開いていない場合) です。このため、開く`HKEY_CLASSES_ROOT\MyVeryOwnKey`を開くと`HasASubKey`で`MyVeryOwnKey`親が開いてよりも高速`MyVeryOwnKey`を閉じて`MyVeryOwnKey`、して開く`MyVeryOwnKey\HasASubKey`です。  
  
## <a name="see-also"></a>関連項目  
 [レジストラー スクリプトの作成](../atl/creating-registrar-scripts.md)

