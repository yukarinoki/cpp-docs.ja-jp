---
description: '詳細情報: domain_error クラス'
title: domain_error クラス
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::domain_error
helpviewer_keywords:
- domain_error class
ms.assetid: a1d8245d-61c2-4d1e-973f-073bd5dd5fa3
ms.openlocfilehash: 337df7c7c8e2327a4e5b88a45a736c697e6cb1bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324489"
---
# <a name="domain_error-class"></a>domain_error クラス

このクラスは、ドメイン エラーを通知するためにスローされる例外すべてに対する基底クラスとして機能します。

## <a name="syntax"></a>構文

```cpp
class domain_error : public logic_error {
public:
    explicit domain_error(const string& message);

    explicit domain_error(const char *message);

};
```

## <a name="remarks"></a>解説

によって返される値 `what()` は、のコピーです `message.data()` 。 詳細については、[`what`](../standard-library/exception-class.md) および [`data`](../standard-library/basic-string-class.md#data) を参照してください。

## <a name="example"></a>例

```cpp
// domain_error.cpp
// compile with: /EHsc /GR
#include <iostream>

using namespace std;

int main( )
{
   try
   {
      throw domain_error( "Your domain is in error!" );
   }
   catch (exception &e)
   {
      cerr << "Caught: " << e.what( ) << endl;
      cerr << "Type: " << typeid(e).name( ) << endl;
   };
}
/* Output:
Caught: Your domain is in error!
Type: class std::domain_error
*/
```

## <a name="requirements"></a>要件

**ヘッダー:**\<stdexcept>

**名前空間:** std

## <a name="see-also"></a>関連項目

[logic_error クラス](../standard-library/logic-error-class.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
