---
title: '&lt;future&gt; 列挙型 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
ms.openlocfilehash: 0056d54844e9396d517fd44c3649f1bc9605829b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700558"
---
# <a name="ltfuturegt-enums"></a>&lt;future&gt; 列挙型

||||
|-|-|-|
|[future_errc](#future_errc)|[future_status](#future_status)|[launch](#launch)|

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

## <a name="see-also"></a>関連項目

[\<future>](../standard-library/future.md)<br/>
