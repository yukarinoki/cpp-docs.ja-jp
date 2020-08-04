---
title: out_of_range クラス
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::out_of_range
helpviewer_keywords:
- out_of_range class
ms.assetid: d0e14dc0-065e-4666-9ac9-51e52223c503
ms.openlocfilehash: 3bbbc48aa2020782594606c6a53a34f7b937fc58
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2020
ms.locfileid: "87521279"
---
# <a name="out_of_range-class"></a>out_of_range クラス

このクラスは、有効範囲外の引数を通知するためにスローされる例外すべてに対する基底クラスとして機能します。

## <a name="syntax"></a>構文

```cpp
class out_of_range : public logic_error {
public:
    explicit out_of_range(const string& message);

    explicit out_of_range(const char *message);

};
```

## <a name="remarks"></a>Remarks

によって返される値 `what()` は、のコピーです `message.data()` 。 詳細については、[`what`](../standard-library/exception-class.md) および [`data`](../standard-library/basic-string-class.md#data) を参照してください。

## <a name="example"></a>例

```cpp
// out_of_range.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

using namespace std;

int main() {
// out_of_range
   try {
      string str( "Micro" );
      string rstr( "soft" );
      str.append( rstr, 5, 3 );
      cout << str << endl;
   }
   catch ( exception &e ) {
      cerr << "Caught: " << e.what( ) << endl;
   };
}
```

## <a name="output"></a>出力

```cpp
Caught: invalid string position
```

## <a name="requirements"></a>必要条件

**ヘッダー:**\<stdexcept>

**名前空間:** std

## <a name="see-also"></a>関連項目

[logic_error クラス](../standard-library/logic-error-class.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
