---
description: '詳細情報: コンパイラの警告 (レベル 1) C4503'
title: コンパイラの警告 (レベル 1) C4503
ms.date: 05/14/2018
f1_keywords:
- C4503
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
ms.openlocfilehash: 4ff438c3ae9e698bdaaf476d022b8914add4169e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294900"
---
# <a name="compiler-warning-level-1-c4503"></a>コンパイラの警告 (レベル 1) C4503

> '*identifier*': 装飾名の長さが制限を超えています。名前が切り詰められました

## <a name="remarks"></a>解説

このコンパイラの警告は互換性のために残されていますが、Visual Studio 2017 以降のコンパイラでは生成されません。

装飾名がコンパイラの制限 (4096) を超えており、切り捨てられました。 この警告と切り捨てを回避するには、引数の数または使用する識別子の名前の長さを減らします。 コンパイラの制限を超える装飾名は、ハッシュが適用され、名前の競合の危険性がありません。

以前のバージョンの Visual Studio を使用している場合、テンプレートに特化したテンプレートがコードに含まれていると、この警告が発行されることがあります。 たとえば、(C++ 標準ライブラリの) マップのマップなどです。 このような状況では、マップを含む typedef を型 (たとえば、) にすることができ **`struct`** ます。

ただし、コードを再構築しないことを決定する場合もあります。  C4503 を生成するアプリケーションを配布することはできますが、切り捨てられたシンボルでリンク時エラーが発生すると、エラーのシンボルの種類を特定するのが困難になることがあります。 デバッグがより困難になることもあります。デバッガーは、シンボル名を型名に難しくなるにマッピングしている可能性があります。 ただし、プログラムの正確性は、切り捨てられた名前の影響を受けません。

## <a name="example"></a>例

次の例では、Visual Studio 2017 より前のコンパイラで C4503 が生成されます。

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

このサンプルでは、C4503 を解決するためにコードを書き換える方法の1つを示します。

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
