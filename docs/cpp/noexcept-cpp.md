---
title: noexcept (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/12/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- noexcept_cpp
dev_langs:
- C++
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a0cc12c5b82e1cb8cda8243020f91614fe840502
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420884"
---
# <a name="noexcept-c"></a>noexcept (C++)
**C++ 11:** 関数が例外をスローするかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
> *noexcept-expression*:  
> &nbsp;&nbsp;&nbsp;&nbsp;**noexcept**  
> &nbsp;&nbsp;&nbsp;&nbsp;**noexcept(** *constant-expression* **)**  
  
### <a name="parameters"></a>パラメーター  
 *constant-expression*  
 型の定数式`bool`潜在的な例外の種類のセットが空かどうかを表すです。 無条件のバージョンは等価`noexcept(true)`です。  
  
## <a name="remarks"></a>コメント  
 A *noexcept 式*一種の*例外指定*関数の宣言が終了した任意の例外の例外ハンドラーによって照合される可能性がありますの種類のセットを表すためのサフィックス、関数。 条件演算子を単項`noexcept(` *constant_expression* `)`場所*constant_expression* yeilds `true`、およびその無条件シノニム`noexcept`、関数を終了できる潜在的な例外の種類のセットが空であるを指定します。 関数は例外をスローし、スコープの外部に伝達する例外を許可しません。 演算子`noexcept(` *constant_expression* `)`場所*constant_expression* yeilds `false`、または例外の指定がない場合 (以外のデストラクターまたは割り当て解除関数) では、関数を終了する可能性がある例外のセットが一連のすべての種類であることを示します。  
 
 関数としてマーク`noexcept`場合にのみそれが呼び出す、直接または間接的に、すべての関数も`noexcept`または`const`です。 コンパイラが最大浮上可能性がある例外のすべてのコード パスを必ずしもチェックは、`noexcept`関数。 かどうか、例外は、マークされた関数の外側のスコープを終了は`noexcept`、 [std::terminate](../standard-library/exception-functions.md#terminate)がすぐに、呼び出されると、任意のスコープ内のオブジェクトのデストラクターが呼び出される保証はありません。 使用して`noexcept`、動的な例外指定子ではなく`throw()`、これは、標準で推奨されなくなりました。 適用することをお勧めします。`noexcept`コール スタックに伝達される例外を許可しないすべての関数。 関数が宣言されている場合`noexcept`、これにより、コンパイラはいくつかの異なるコンテキストでより効率的なコードを生成します。 詳細については、次を参照してください。[例外指定](exception-specifications-throw-cpp.md)です。   
  
## <a name="example"></a>例  
テンプレートをコピーする関数の引数を宣言することがあります`noexcept`あるという条件でコピーされるオブジェクトがプレーンな古いデータ型 (POD)。 このような関数は、次のように宣言することができます。  
  
```cpp  
#include <type_traits>  
  
template <typename T>  
T copy_object(const T& obj) noexcept(std::is_pod<T>)  
{  
   // ...   
}  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ 例外処理](cpp-exception-handling.md)[例外の仕様 (スロー、noexcept)](exception-specifications-throw-cpp.md)