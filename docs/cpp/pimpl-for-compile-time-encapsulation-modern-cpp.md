---
title: コンパイル時 (Modern C) をカプセル化の Pimpl |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2e80c4bd86cd4c7400e3937fcb8d164fe6b14106
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404656"
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>コンパイル時のカプセル化の Pimpl (Modern C++)
*Pimpl イディオム*はインターフェイスを分離したり結合度を最小限に抑えるの実装を非表示にする最新の C++ 手法です。 Pimpl は省略形で"実装へのポインター" 既にある概念を理解できます。 ただし Cheshire Cat またはコンパイラのファイアウォールの表現形式のような他の名前を知っています。  
  
## <a name="why-use-pimpl"></a>Pimpl を使用する理由  
 Pimpl 表現形式を使用して、ソフトウェア開発ライフ サイクルを改善する方法を次に示します。  
  
-   コンパイルの依存関係の最小化します。  
  
-   インターフェイスと実装の分離。  
  
-   移植性。  
  
## <a name="pimpl-header"></a>Pimpl ヘッダー  
  
```cpp  
// my_class.h  
class my_class {  
   //  ... all public and protected stuff goes here ...  
private:  
   class impl; unique_ptr<impl> pimpl; // opaque type here  
};  
```  
  
 Pimpl 表現形式は、再構築を連鎖と不安定オブジェクトのレイアウトを回避できます。 (推移的) 人気のある型にも適しています。  
  
## <a name="pimpl-implementation"></a>Pimpl 実装  
 定義、 `impl` .cpp ファイル内のクラス。  
  
```cpp  
// my_class.cpp  
class my_class::impl {  // defined privately here  
  // ... all private data and functions: all of these  
  //     can now change without recompiling callers ...  
};  
my_class::my_class(): pimpl( new impl )  
{  
  // ... set impl values ...   
}  
```  
  
## <a name="best-practices"></a>ベスト プラクティス  
 スローしないスワップの特殊化のサポートを追加するかどうかを検討してください。  
  
## <a name="see-also"></a>関連項目  
 [C++ へようこそ](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)