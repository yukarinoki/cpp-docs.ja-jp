---
title: For each を使用して、C++ 標準ライブラリ コレクションに対する繰り返し処理 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- DTL collections, iterating over
ms.assetid: 9358ca29-b982-4a19-bbfd-bef50fe66c9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 92934e3f00bb34e6adfe101b0fea7abbe03600c2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383197"
---
# <a name="iterating-over-c-standard-library-collection-by-using-for-each"></a>For each を使用して、C++ 標準ライブラリのコレクションを反復処理します。

`for each`キーワードを使用して、C++ 標準ライブラリ コレクションを反復処理することができます。

## <a name="all-platforms"></a>すべてのプラットフォーム

C++ 標準ライブラリ コレクションとも呼ばれますが、*コンテナー*します。 詳細については、「[C++ Standard Library Containers (C++ 標準ライブラリ コンテナ―)](../standard-library/stl-containers.md)」をご覧ください。

## <a name="examples"></a>使用例

次のコード例では`for each`を反復処理する、 [\<マップ >](../standard-library/map.md)します。

```cpp
// for_each_stl.cpp
// compile with: /EHsc
#include <map>
#include <iostream>
#include <string>
using namespace std;

int main() {
   int retval  = 0;
   map<string, int> months;

   months["january"] = 31;
   months["february"] = 28;
   months["march"] = 31;
   months["april"] = 30;
   months["may"] = 31;
   months["june"] = 30;
   months["july"] = 31;
   months["august"] = 31;
   months["september"] = 30;
   months["october"] = 31;
   months["november"] = 30;
   months["december"] = 31;

   map<string, int> months_30;

   for each( pair<string, int> c in months )
      if ( c.second == 30 )
         months_30[c.first] = c.second;

   for each( pair<string, int> c in months_30 )
      retval++;

   cout << "Months with 30 days = " << retval << endl;
}
```

### <a name="output"></a>出力

```Output
Months with 30 days = 4
```

## <a name="example"></a>例

次のコード例は、const 参照を使用 (`const&`) の C++ 標準ライブラリ コンテナーの反復変数。 参照を使用することができます (`&`) として宣言できる型の任意のコレクションの反復変数として、 *T*`&`します。

```cpp
// for_each_stl_2.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>
using namespace std;

int main() {
   int retval = 0;

   vector<int> col(3);
   col[0] = 10;
   col[1] = 20;
   col[2] = 30;

   for each( const int& c in col )
      retval += c;

   cout << "retval: " << retval << endl;
}
```

### <a name="output"></a>出力

```Output
retval: 60
```

## <a name="windows-runtime"></a>Windows ランタイム

プラットフォーム固有の解説については、この機能はありません。

### <a name="requirements"></a>要件

コンパイラ オプション: **/ZW**

## <a name="common-language-runtime"></a>共通言語ランタイム

プラットフォーム固有の解説については、この機能はありません。

### <a name="requirements"></a>要件

コンパイラ オプション: **/clr**

## <a name="see-also"></a>関連項目

[for each、in](../dotnet/for-each-in.md)<br/>
[ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)