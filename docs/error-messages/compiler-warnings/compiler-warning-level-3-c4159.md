---
title: コンパイラの警告 (レベル 3) C4159
ms.date: 11/04/2016
f1_keywords:
- C4159
helpviewer_keywords:
- C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
ms.openlocfilehash: 20d6010cb83107946c00f2f7b00cda771b2e70b9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199018"
---
# <a name="compiler-warning-level-3-c4159"></a>コンパイラの警告 (レベル 3) C4159

> #<a name="pragma-pragmapop--has-popped-previously-pushed-identifier-identifier"></a>pragma pragma (pop,...): 以前にプッシュされた識別子 '*identifier*' がポップされました

## <a name="remarks"></a>解説

ソースコードには、プラグマの識別子を持つ**プッシュ**命令と、識別子のない**pop**命令が含まれています。 その結果、*識別子*がポップされ、その後の*識別子*の使用によって予期しない動作が発生する可能性があります。

## <a name="example"></a>例

この警告を回避するには、 **pop**命令で識別子を指定します。 次に例を示します。

```cpp
// C4159.cpp
// compile with: /W3
#pragma pack(push, f)
#pragma pack(pop)   // C4159

// using the identifier resolves the warning
// #pragma pack(pop, f)

int main()
{
}
```
