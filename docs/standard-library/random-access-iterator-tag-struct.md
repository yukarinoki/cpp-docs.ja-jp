---
title: random_access_iterator_tag 構造体 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xutility/std::random_access_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- random_access_iterator_tag class
- random_access_iterator_tag struct
ms.assetid: 59f5b741-c5b4-459c-ad0a-3b67cddeea23
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e911d91e987bb5172d9681161dcd87a287201b4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853779"
---
# <a name="randomaccessiteratortag-struct"></a>random_access_iterator_tag 構造体

ランダム アクセス反復子を表す **iterator_category** 関数の戻り値の型を提供するクラス。

## <a name="syntax"></a>構文

```cpp
struct random_access_iterator_tag    : public bidirectional_iterator_tag {};
```

## <a name="remarks"></a>コメント

カテゴリ タグ クラスはアルゴリズムの選択にコンパイル タグとして使用されます。 テンプレート関数は、コンパイル時に最も効率的なアルゴリズムを利用できるように、その反復子引数の最も具体的なカテゴリを見つける必要があります。 `Iterator` 型の反復子ごとに、反復子の動作を表す最も具体的なカテゴリ タグとして `iterator_traits`< `Iterator`> **::iterator_category** を定義する必要があります。

この型は、**Iter** がランダム アクセス反復子としてサービスを提供するオブジェクトを表すとき、**iterator**\< **Iter**> **::iterator_category** と同じになります。

## <a name="example"></a>例

```cpp
// iterator_rait.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>
#include <list>

using namespace std;

int main( )
{
   vector<int> vi;
   vector<char> vc;
   list<char> lc;
   iterator_traits<vector<int>:: iterator>::iterator_category cati;
   iterator_traits<vector<char>:: iterator>::iterator_category catc;
   iterator_traits<list<char>:: iterator>::iterator_category catlc;

   // These are both random-access iterators
   cout << "The type of iterator for vector<int> is "
       << "identified by the tag:\n "
       << typeid ( cati ).name( ) << endl;
   cout << "The type of iterator for vector<char> is "
       << "identified by the tag:\n "
       << typeid ( catc ).name( ) << endl;
   if ( typeid ( cati ) == typeid( catc ) )
      cout << "The iterators are the same." << endl << endl;
   else
      cout << "The iterators are not the same." << endl << endl;

   // But the list iterator is bidirectinal, not random access
   cout << "The type of iterator for list<char> is "
       << "identified by the tag:\n "
       << typeid (catlc).name( ) << endl;

   // cout << ( typeid ( vi.begin( ) ) == typeid( vc.begin( ) ) ) << endl;
   if ( typeid ( vi.begin( ) ) == typeid( vc.begin( ) ) )
      cout << "The iterators are the same." << endl;
   else
      cout << "The iterators are not the same." << endl;
   // A random-access iterator is a bidirectional iterator.
   cout << ( void* ) dynamic_cast< iterator_traits<list<char>:: iterator>
          ::iterator_category* > ( &catc ) << endl;
}
```

## <a name="sample-output"></a>出力例

次の出力は x86 のものです。

```Output
The type of iterator for vector<int> is identified by the tag:
    struct std::random_access_iterator_tag
The type of iterator for vector<char> is identified by the tag:
    struct std::random_access_iterator_tag
The iterators are the same.

The type of iterator for list<char> is identified by the tag:
    struct std::bidirectional_iterator_tag
The iterators are not the same.
0012FF3B
```

## <a name="requirements"></a>要件

**ヘッダー:** \<iterator>

**名前空間:** std

## <a name="see-also"></a>関連項目

[bidirectional_iterator_tag 構造体](../standard-library/bidirectional-iterator-tag-struct.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
