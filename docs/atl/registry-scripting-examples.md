---
title: レジストリ スクリプトの例 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- scripting, examples
- registrar scripts [ATL]
- scripts, Registrar scripts
- registry, Registrar
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c192e8bec1d32dd7d7a7953e5da72a139c7520e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361890"
---
# <a name="registry-scripting-examples"></a>レジストリ スクリプトの例
このトピックでは、スクリプトの例では、システム レジストリにキーを追加、レジストラー COM サーバーを登録および複数のパース ツリーを指定する方法を示します。  
  
## <a name="add-a-key-to-hkeycurrentuser"></a>HKEY_CURRENT_USER にキーを追加します。  
 次のパース ツリーは、システム レジストリに 1 つのキーを追加する単純なスクリプトを示しています。 具体的には、スクリプトは、キーに追加`MyVeryOwnKey`を`HKEY_CURRENT_USER`です。 既定の文字列値としても割り当てます`HowGoesIt`新しいキー。  
  
```  
HKEY_CURRENT_USER  
{  
 'MyVeryOwnKey' = s 'HowGoesIt'  
}  
```  
  
 このスクリプトは、複数のサブキーを次のように定義に簡単に拡張できます。  
  
```  
HKCU  
{  
 'MyVeryOwnKey' = s 'HowGoesIt'  
 {  
 'HasASubkey'  
 {  
 'PrettyCool' = d '55'  
    val 'ANameValue' = s 'WithANamedValue'  
 }  
 }  
}  
```  
  
 ここで、スクリプトは、サブキーを追加します。`HasASubkey`を`MyVeryOwnKey`です。 このサブキーに追加されます両方、`PrettyCool`サブキー (、既定値`DWORD`55 の値)、および`ANameValue`value という名前の (の文字列値を持つ`WithANamedValue`)。  
  
##  <a name="_atl_register_the_registrar_com_server"></a> レジストラー COM サーバーを登録します。  
 次のスクリプトは、レジストラー COM サーバー自体を登録します。  
  
```  
HKCR  
{  
    ATL.Registrar = s 'ATL Registrar Class'  
 {  
    CLSID = s '{44EC053A-400F-11D0-9DCD-00A0C90391D3}'  
 }  
    NoRemove CLSID  
 {  
    ForceRemove {44EC053A-400F-11D0-9DCD-00A0C90391D3} = 
    s 'ATL Registrar Class'  
 {  
    ProgID = s 'ATL.Registrar'  
    InprocServer32 = s '%MODULE%'  
 {  
    val ThreadingModel = s 'Apartment'  
 }  
 }  
 }  
}  
```  
  
 この解析ツリーを追加、実行時に、`ATL.Registrar`キーを`HKEY_CLASSES_ROOT`です。 この新しいキーにし、it:  
  
-   指定`ATL Registrar Class`キーの既定の文字列値として。  
  
-   追加`CLSID`サブキーとして。  
  
-   指定`{44EC053A-400F-11D0-9DCD-00A0C90391D3}`の`CLSID`します。 (この値は、レジストラーので使用するための CLSID `CoCreateInstance`)。  
  
 `CLSID`は、共有、削除しないで登録解除モードでします。 このステートメントでは、`NoRemove CLSID`は、ことを示すことで`CLSID`レジスタ モードで開かれているし、登録解除モードでは無視する必要があります。  
  
 `ForceRemove`ステートメントがキーを再作成する前に、キーとそのすべてのサブキーを削除することで、ハウスキーピング機能を提供します。 サブキーの名前が変更された場合に役立ちます。 これができます。 このスクリプトの例では`ForceRemove`かどうかをチェック`{44EC053A-400F-11D0-9DCD-00A0C90391D3}`既に存在します。 その場合、 `ForceRemove`:  
  
-   再帰的に削除`{44EC053A-400F-11D0-9DCD-00A0C90391D3}`とそのすべてのサブキーです。  
  
-   再作成`{44EC053A-400F-11D0-9DCD-00A0C90391D3}`です。  
  
-   追加`ATL Registrar Class`の既定の文字列値として`{44EC053A-400F-11D0-9DCD-00A0C90391D3}`です。  
  
 解析ツリーに 2 つの新しいサブキーを今すぐ追加`{44EC053A-400F-11D0-9DCD-00A0C90391D3}`です。 最初のキー `ProgID`ProgID は、既定の文字列値を取得します。 2 番目のキー `InprocServer32`、既定の文字列値を取得`%MODULE%`、つまり、」に説明されているプリプロセッサ値[置き換え可能パラメーターの使用 (レジストラーのプリプロセッサ)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)、この記事のです。 `InprocServer32` また、名前付きの値を取得`ThreadingModel`の文字列値を持つ`Apartment`します。  
  
## <a name="specify-multiple-parse-trees"></a>複数のパース ツリーを指定します。  
 1 つ以上の解析ツリーをスクリプトを指定するには、別の最後に 1 つのツリーを配置します。 たとえば、次のスクリプトが、キーを追加`MyVeryOwnKey`、両方のパース ツリーを`HKEY_CLASSES_ROOT`と`HKEY_CURRENT_USER`:  
  
```  
HKCR  
{  
 'MyVeryOwnKey' = s 'HowGoesIt'  
}  
HKEY_CURRENT_USER  
{  
 'MyVeryOwnKey' = s 'HowGoesIt'  
}  
```  
  
> [!NOTE]
>  レジストラー スクリプトでは、トークンの最大サイズは 4 K です。 (トークンは、構文内の認識可能な要素です)。前のスクリプトの例で`HKCR`、 `HKEY_CURRENT_USER`、 `'MyVeryOwnKey'`、および`'HowGoesIt'`すべてトークンです。  
  
## <a name="see-also"></a>関連項目  
 [レジストラー スクリプトの作成](../atl/creating-registrar-scripts.md)

