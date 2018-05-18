---
title: コンパイラの警告 (レベル 1) C4503 |Microsoft ドキュメント
ms.custom: ''
ms.date: 05/14/2018
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
ms.openlocfilehash: f60fdb44c5368ccc5c5f089002614332d95a63fe
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="compiler-warning-level-1-c4503"></a>コンパイラの警告 (レベル 1) C4503

> '*識別子*': 装飾名の長さを超えると、名前は切り詰められました

## <a name="remarks"></a>コメント

このコンパイラの警告は今後使用しませんし、Visual Studio 2017 およびそれ以降のコンパイラでは生成されません。

装飾名はコンパイラの制限 (4096) よりも長い、切り捨てられました。 この警告は、切り捨てを回避するのには、引数の数または使用される識別子の名前の長さを減らしてください。 装飾名をコンパイラの制限を超える適用されたハッシュがあり、名前の競合の危険性はありません。

コードには、テンプレートが含まれている場合、この警告が発行されることができます、古いバージョンの Visual Studio を使用して、ときに繰り返しのテンプレートに特化しました。 たとえば、マップ (C++ 標準ライブラリ) からマップします。 このような状況で行うことができます、typedef 型 (、**構造体**など) を含むマップします。

、ただし、する場合、コードを再構築されません。  C4503 を生成するアプリケーションを出荷することが切り捨てられたシンボルで、リンク時のエラーが発生した場合、できるエラー内の記号の種類を確認することは困難です。 月もデバッグするより難しくなります。デバッガーは、型名にシンボル名を困難になるからマッピングがあります。 ただし、切り捨てられた名前によって影響を受けるは、プログラムの正確さです。

## <a name="example"></a>例

次の例では、Visual Studio 2017 する前にコンパイラで C4503 が生成されます。

```cpp
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

このサンプルは、C4503 を解決するのには、コードを書き換えるの 1 つの方法を示しています。

```cpp
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