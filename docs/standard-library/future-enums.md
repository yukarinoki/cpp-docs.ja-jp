---
title: '&lt;future&gt; 列挙型'
ms.date: 11/04/2016
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
ms.openlocfilehash: a5bcebd80b296a0b8416580aa03acc59ce3750cd
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865175"
---
# <a name="ltfuturegt-enums"></a>&lt;future&gt; 列挙型

||||
|-|-|-|
|[future_errc](#future_errc)|[future_status](#future_status)|[開い](#launch)|

## <a name="future_errc"></a>  future_errc 列挙型

[future_error](../standard-library/future-error-class.md) クラスによって報告されるすべてのエラーのシンボル名を提供します。

```cpp
class future_errc {
   broken_promise,
   future_already_retrieved,
   promise_already_satisfied,
   no_state
   };
```

## <a name="future_status"></a>  future_status 列挙型

期限が設定された wait 関数から返される理由のシンボル名を提供します。

```cpp
enum future_status{
    ready,
    timeout,
    deferred
};
```

## <a name="launch"></a>  launch 列挙型

テンプレート関数 [async](../standard-library/future-functions.md#async) で使用できるモードを示すビットマスク型を表します。

```cpp
class launch{
   async,
   deferred
   };
```

## <a name="see-also"></a>参照

[\<future>](../standard-library/future.md)
