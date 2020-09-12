---
title: コンパイラの警告 (レベル 1) C4055
ms.date: 11/04/2016
f1_keywords:
- C4055
helpviewer_keywords:
- C4055
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
ms.openlocfilehash: 47883f60c3205125a8ee88b804c1d622b3ba0b41
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041030"
---
# <a name="compiler-warning-level-1-c4055"></a>コンパイラの警告 (レベル 1) C4055

> '*conversion*': データポインター ' type1 ' から関数*ポインター '**type1*' へ

## <a name="remarks"></a>注釈

**廃止:** この警告は、Visual Studio 2017 以降のバージョンでは生成されません。

データポインターが、誤って関数ポインターにキャストされています。 これは /Za ではレベル 1 の警告になり、/Ze ではレベル 4 の警告になります。

## <a name="example"></a>例

次の例では C4055 が生成されます。

```C
// C4055.c
// compile with: /Za /W1 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
   return (PFUNC)pi;   // C4055
}
```

これは、/Ze ではレベル 4 の警告です。

```C
// C4055b.c
// compile with: /W4 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
return (PFUNC)pi;   // C4055
}
```
