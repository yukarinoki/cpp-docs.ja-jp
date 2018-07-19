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
ms.openlocfilehash: d30ad23956c978ee47ef447463a0d5422a94d4b9
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962323"
---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt; 関数

これらで定義されたグローバル テンプレート関数は、 &lt;ostream&gt;します。 メンバー関数は、次を参照してください。、 [basic_ostream クラス](basic-ostream-class.md)ドキュメント。

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

*Ostr*型のオブジェクト**basic_ostream**します。

*Tr*文字の特徴です。

### <a name="return-value"></a>戻り値

型のオブジェクト**basic_ostream**します。

### <a name="remarks"></a>Remarks

マニピュレーターが*Ostr*.[put](../standard-library/basic-ostream-class.md#put)(*Ostr*.[拡大変換](../standard-library/basic-ios-class.md#widen)('\n'))、号餧ェヒェマル*Ostr*.[フラッシュ](../standard-library/basic-ostream-class.md#flush)します。 返します*Ostr*します。

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

*Ostr*型のオブジェクト`basic_ostream`します。

*Tr*文字の特徴です。

### <a name="return-value"></a>戻り値

`basic_ostream` 型のオブジェクト。

### <a name="remarks"></a>Remarks

マニピュレーターが*Ostr*.[put](../standard-library/basic-ostream-class.md#put)(*Elem*('\0'))。 返します*Ostr*します。

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

*Ostr*型のオブジェクト`basic_ostream`します。

*Tr*文字の特徴です。

### <a name="return-value"></a>戻り値

`basic_ostream` 型のオブジェクト。

### <a name="remarks"></a>Remarks

マニピュレーターが*Ostr*.[フラッシュ](../standard-library/basic-ostream-class.md#flush)します。 返します*Ostr*します。

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

2 つの `basic_ostream` オブジェクトの値を交換します。

```cpp
template <class Elem, class Tr>
void swap(
   basic_ostream<Elem, Tr>& left,
   basic_ostream<Elem, Tr>& right);
```

### <a name="parameters"></a>パラメーター

*Elem*要素の型。

*Tr*文字の特徴です。

*左*への左辺値参照を`basic_ostream`オブジェクト。

*適切な*への左辺値参照を`basic_ostream`オブジェクト。

### <a name="remarks"></a>Remarks

テンプレート関数 `swap` は、`left.swap(right)` を実行します。

## <a name="see-also"></a>関連項目

[\<ostream>](../standard-library/ostream.md)
