---
title: コンパイラの警告 (レベル 1) C4503 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4503
dev_langs:
- C++
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adafddff679cbe04cf26a39647760bf595af0bd3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4503"></a>コンパイラの警告 (レベル 1) C4503
'identifier': 装飾名の長さを超えると、名前は切り詰められました  
  
 装飾名はコンパイラの制限 (4096) よりも長い、切り捨てられました。 この警告は、切り捨てを回避するのには、引数の数または使用される識別子の名前の長さを減らしてください。  
  
 この警告が発行される状況の 1 つは、コードが含まれているテンプレートに繰り返しテンプレートの特殊化です。  たとえば、マップ (C++ 標準ライブラリ) からマップします。  このような状況で、マップを含んでいる型 (たとえば構造体など)、typedef を作成できます。  
  
 、ただし、する場合、コードを再構築されません。  C4503 を生成するアプリケーションを出荷することは、切り捨てられたシンボルで、リンク時のエラーが発生した場合エラー内の記号の種類を確認することが難しくなります。  デバッグも難しくなります。デバッガーでは、困難になるからシンボル名を型名をマッピングすることがあります。  ただし、切り捨てられた名前によって影響を受けるは、プログラムの正確さです。  
  
 次の例では、C4503 が生成されます。  
  
```  
// C4503.cpp  
// compile with: /W1 /EHsc /c  
// C4503 expected  
#include <string>  
#include <map>  
  
class Field{};  
  
typedef std::map<std::string, Field> Screen;  
typedef std::map<std::string, Screen> WebApp;  
typedef std::map<std::string, WebApp> WebAppTest;  
typedef std::map<std::string, WebAppTest> Hello;  
Hello MyWAT;  
```  
  
 次の例は、C4503 を解決するのには、コードを書き換えるの 1 つの方法を示しています。  
  
```  
// C4503b.cpp  
// compile with: /W1 /EHsc /c  
#include <string>  
#include <map>  
  
class Field{};  
struct Screen2 {  
   std::map<std::string, Field> Element;  
};  
  
struct WebApp2 {  
   std::map<std::string, Screen2> Element;  
};  
  
struct WebAppTest2 {  
   std::map<std::string, WebApp2> Element;  
};  
  
struct Hello2 {  
   std::map<std::string, WebAppTest2> Element;  
};  
  
Hello2 MyWAT2;  
```