---
title: 転送先の型 (C + + CLI) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- type forwarding, Visual C++
ms.assetid: ae730b69-0c27-41cc-84e1-3132783866ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9caa2e18a1ec851967857eb068797e092835f587
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891095"
---
# <a name="type-forwarding-ccli"></a>型の転送 (C++/CLI)
*転送先の入力*アセンブリ A を使用するクライアントを再コンパイルする必要がないようにに、1 つのアセンブリ (アセンブリ A) から型を別のアセンブリ (アセンブリ B) に移動することができます  
  
## <a name="all-platforms"></a>すべてのプラットフォーム  
 この機能はすべてのランタイムでサポートされていません。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 この機能は、Windows ランタイムでサポートされていません。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/ZW**  
  
## <a name="common-language-runtime"></a>共通言語ランタイム  
 次のコード例では、型の転送を使用する方法を示します。  
  
### <a name="syntax"></a>構文  
  
```  
#using "new.dll"  
[assembly:TypeForwardedTo(type::typeid)];  
```  
  
### <a name="parameters"></a>パラメーター  
 `new`  
 型定義の移動先のアセンブリ。  
  
 `type`  
 型定義に含まれる別のアセンブリに移動します。  
  
### <a name="remarks"></a>コメント  
 コンポーネント (アセンブリ) が付属していて、後にクライアント アプリケーションによって使用されているを使用する型のコンポーネント (アセンブリ) からの型を別のアセンブリに移動、更新されたコンポーネント (および必要な追加のアセンブリ) を出荷する転送とクライアントアプリケーションは、再コンパイルせずに引き続き動作します。  
  
 型の転送は、既存のアプリケーションによって参照されるコンポーネントに対してのみ機能します。 アプリケーションをリビルドするときに、アプリケーションで使用されている型の適切なアセンブリ参照が必要があります。  
  
 追加する必要がありますアセンブリから型 (型 A) を転送するとき、`TypeForwardedTo`アセンブリ参照と、その型の属性です。 参照されているアセンブリには、次のいずれかを含める必要があります。  
  
-   タイプ a の定義  
  
-   A`TypeForwardedTo`アセンブリ参照と同様に、a の種類の属性です。  
  
 転送できる種類の例は次のとおりです。  
  
-   ref クラス  
  
-   値クラス  
  
-   列挙型  
  
-   インターフェイス  
  
 次の種類を転送することはできません。  
  
-   ジェネリック型  
  
-   ネイティブ型  
  
-   入れ子にされた型 (入れ子にされた型を転送する場合は、する必要がありますを転送するそれを囲む型)  
  
 型は、共通言語ランタイムを対象とする任意の言語で作成されたアセンブリに転送できます。  
  
 A.dll の組み立てに使用されるソース コード ファイルには、型定義が含まれている場合、(`ref class MyClass`)、その型を移動するとアセンブリ B.dll に定義。  
  
1.  移動、 `MyClass` B.dll をビルドするために使用のソース コード ファイルに定義を入力します。  
  
2.  アセンブリ B.dll をビルドします。  
  
3.  削除、 `MyClass` A.dll をビルドし、次の置換に使用されるソース コードからの定義を入力します。  
  
    ```  
    #using "B.dll"  
    [assembly:TypeForwardedTo(MyClass::typeid)];  
    ```  
  
4.  A.dll のアセンブリをビルドします。  
  
5.  クライアント アプリケーションを再コンパイルしなくても A.dll を使用します。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/clr**