---
title: '&lt;ostream&gt; 関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ostream/std::swap
- ostream/std::endl
- ostream/std::ends
- ostream/std::flush
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
helpviewer_keywords:
- std::swap [C++]
- std::endl [C++]
- std::ends [C++]
- std::flush [C++]
ms.openlocfilehash: e85ce2728aaaa8ae9b23067bfb1dcbb3ff2db7d0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt; 関数

これらで定義されたグローバル テンプレート関数は、 &lt;ostream&gt;です。 メンバー関数の場合は、次を参照してください。、 [basic_ostream クラス](basic-ostream-class.md)ドキュメント。

||||
|-|-|-|
|[endl](#endl)|[ends](#ends)|[flush](#flush)|
|[swap](#swap)|

## <a name="endl"></a>endl

行を終了し、バッファーをフラッシュします。

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& endl(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>パラメーター

*Elem*要素の型。

*Ostr*型のオブジェクト**basic_ostream**です。

*Tr*文字の特徴 (traits)。

### <a name="return-value"></a>戻り値

型のオブジェクト**basic_ostream**です。

### <a name="remarks"></a>コメント

マニピュレーター呼び出し*Ostr*.[put](../standard-library/basic-ostream-class.md#put)(*Ostr*.[拡大変換](../standard-library/basic-ios-class.md#widen)('\n'))、しを呼び出して*Ostr*.[フラッシュ](../standard-library/basic-ostream-class.md#flush)です。 返します*Ostr*です。

### <a name="example"></a>例

```cpp
// ostream_endl.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "testing" << endl;
}
```

```Output
testing
```

## <a name="ends"></a>終点

文字列を終了します。

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& ends(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>パラメーター

*Elem*要素の型。

*Ostr*型のオブジェクト**basic_ostream**です。

*Tr*文字の特徴 (traits)。

### <a name="return-value"></a>戻り値

型のオブジェクト**basic_ostream**です。

### <a name="remarks"></a>コメント

マニピュレーター呼び出し*Ostr*.[put](../standard-library/basic-ostream-class.md#put)(*Elem*('\0'))。 返します*Ostr*です。

### <a name="example"></a>例

```cpp
// ostream_ends.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "a";
   cout << "b" << ends;
   cout << "c" << endl;
}
```

```Output
ab c
```

## <a name="flush"></a>flush

バッファーをフラッシュします。

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& flush(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>パラメーター

*Elem*要素の型。

*Ostr*型のオブジェクト**basic_ostream**です。

*Tr*文字の特徴 (traits)。

### <a name="return-value"></a>戻り値

型のオブジェクト**basic_ostream**です。

### <a name="remarks"></a>コメント

マニピュレーター呼び出し*Ostr*.[フラッシュ](../standard-library/basic-ostream-class.md#flush)です。 返します*Ostr*です。

### <a name="example"></a>例

```cpp
// ostream_flush.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "testing" << flush;
}
```

```Output
testing
```

## <a name="swap"></a>swap

2 つの値を交換**basic_ostream**オブジェクト。

```cpp
template <class Elem, class Tr>
void swap(
   basic_ostream<Elem, Tr>& left,
   basic_ostream<Elem, Tr>& right);
```

### <a name="parameters"></a>パラメーター

*Elem*要素の型。

*Tr*文字の特徴 (traits)。

*左*への左辺値参照、 **basic_ostream**オブジェクト。

*右*への左辺値参照、 **basic_ostream**オブジェクト。

### <a name="remarks"></a>コメント

このテンプレート関数は**スワップ**実行`left.swap(right)`です。

## <a name="see-also"></a>関連項目

[\<ostream>](../standard-library/ostream.md)
