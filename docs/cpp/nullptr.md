---
title: nullptr |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- nullptr_cpp
dev_langs:
- C++
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1bcfee3f408f6815e51740f9fc02d842afaa4d5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32419644"
---
# <a name="nullptr"></a>nullptr
任意の生ポインター型に変換可能な `std::nullptr_t` 型の null ポインター定数を指定します。  ヘッダーを含めずに `nullptr` キーワードを使用できますが、コードで `std::nullptr_t` 型を使用する場合、`<cstddef>` ヘッダーを含めることにより定義を行う必要があります。  
  
> [!NOTE]
>  また `nullptr` キーワードは、マネージ コード アプリケーション用に C++/CLI でも定義されており、ISO 標準の C++ キーワードに対して互換性がありません。 使用して、コードをコンパイルする場合がある場合、 [/clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションは、マネージ コードをターゲットを使用して`__nullptr`のすべての行のコードをコンパイラがネイティブな C++ 解釈を使用することを保証する必要があります。 詳細については、次を参照してください。 [nullptr](../windows/nullptr-cpp-component-extensions.md)です。  
  
## <a name="remarks"></a>コメント  
 null ポインター定数として `NULL` またはゼロ (`0`) を使用しないでください。`nullptr` は悪用に対する脆弱性が少なく、大半の状況でより適切に動作します。  たとえば、`func(std::pair<const char *, double>)` が指定されている場合に、`func(std::make_pair(NULL, 3.14))` を呼び出すとコンパイラ エラーが発生します。  NULL マクロは `0` に展開します。したがって、`std::make_pair(0, 3.14)` の呼び出しでは、func() の `std::pair<int, double>` パラメーター型に変換可能ではない `std::pair<const char *, double>` が返されます。  `func(std::make_pair(nullptr, 3.14))` は `std::make_pair(nullptr, 3.14)` に変換可能な `std::pair<std::nullptr_t, double>` を返すので、`std::pair<const char *, double>` の呼び出しは正常にコンパイルされます。  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)   
 [nullptr](../windows/nullptr-cpp-component-extensions.md)