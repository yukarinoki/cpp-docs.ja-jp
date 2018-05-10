---
title: naked (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- naked_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], naked
- naked __declspec keyword
ms.assetid: 69723241-05e1-439b-868e-20a83a16ab6d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 84e172c24bbb87f9243a4c0de25a98c90e043acc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="naked-c"></a>naked (C++)
**Microsoft 固有の仕様**  
  
 `naked` 属性を指定して宣言されている関数の場合、コンパイラでプロローグおよびエピローグ コードのないコードが生成されます。 この機能を使用して、プロローグとエピローグのコード シーケンスをインライン アセンブラー コードで独自に記述できます。 naked 関数は、仮想デバイス ドライバーの記述用に特に便利です。  `naked` 属性は x86 と ARM でのみ有効であり、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] では使用できないことに注意してください。  
  
## <a name="syntax"></a>構文  
  
```  
__declspec(naked) declarator  
```  
  
## <a name="remarks"></a>コメント  
 `naked`属性は、関数の定義に関連するのみされていない型修飾子、naked 関数は、拡張属性構文を使用する必要があります、 [_ _declspec](../cpp/declspec.md)キーワード。  
  

 関数も付いて場合でも、コンパイラが、naked 属性でマークされた関数のインライン関数を生成することはできません、 [_ _forceinline](inline-functions-cpp.md)キーワード。  

  
 メンバーではないメソッドの定義以外のすべてに `naked` 属性が適用されている場合、コンパイラ エラーが発生します。  
  
## <a name="examples"></a>使用例  
 次のコードは `naked` 属性の関数を定義します。  
  
```  
__declspec( naked ) int func( formal_parameters ) {}  
```  
  
 または、次のようにします。  
  
```  
#define Naked __declspec( naked )  
Naked int func( formal_parameters ) {}  
```  
  
 `naked` 属性は、関数のプロローグとエピローグのコード シーケンスをコンパイラが生成するかどうかにのみ影響を与えます。 このような関数を呼び出すために生成されるコードには影響を与えません。 したがって、`naked` 属性は関数の型の一部と見なされず、関数ポインターは `naked` 属性を持つことができません。 さらに、`naked` 属性は、データ定義に適用できません。 たとえば、次のサンプル コードはエラーになります。  
  
```  
__declspec( naked ) int i;       // Error--naked attribute not  
                                 // permitted on data declarations.  
```  
  
 `naked` 属性は、関数定義にだけ関連し、関数のプロトタイプでは指定できません。 たとえば、次の宣言はコンパイラ エラーになります。  
  
```  
__declspec( naked ) int func();  // Error--naked attribute not   
                                 // permitted on function declarations  
```  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [naked 関数呼び出し](../cpp/naked-function-calls.md)