---
description: '詳細情報: overflow_error クラス'
title: overflow_error クラス
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::overflow_error
helpviewer_keywords:
- overflow_error class
ms.assetid: bae7128d-e36b-4a45-84f1-2f89da441d20
ms.openlocfilehash: 48d30974152089d941e9ba7c36deb2d8db3a2501
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340880"
---
# <a name="overflow_error-class"></a>overflow_error クラス

このクラスは、算術オーバーフローを通知するためにスローされる例外すべてに対する基底クラスとして機能します。

## <a name="syntax"></a>構文

```cpp
class overflow_error : public runtime_error {
public:
    explicit overflow_error(const string& message);

    explicit overflow_error(const char *message);

};
```

## <a name="remarks"></a>解説

によって返される値 `what()` は、のコピーです `message.data()` 。 詳細については、[`what`](../standard-library/exception-class.md) および [`data`](../standard-library/basic-string-class.md#data) を参照してください。

## <a name="example"></a>例

```cpp
// overflow_error.cpp
// compile with: /EHsc /GR
#include <bitset>
#include <iostream>

using namespace std;

int main( )
{
   try
   {
      bitset< 33 > bitset;
      bitset[32] = 1;
      bitset[0] = 1;
      unsigned long x = bitset.to_ulong( );
   }
   catch ( exception &e )
   {
      cerr << "Caught " << e.what( ) << endl;
      cerr << "Type " << typeid( e ).name( ) << endl;
   };
}
/* Output:
Caught bitset<N> overflow
Type class std::overflow_error
*/
```

## <a name="requirements"></a>要件

**ヘッダー:**\<stdexcept>

**名前空間:** std

## <a name="see-also"></a>関連項目

[runtime_error クラス](../standard-library/runtime-error-class.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
