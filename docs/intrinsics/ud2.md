---
description: '詳細については、次を参照してください: __ud2'
title: __ud2
ms.date: 09/02/2019
f1_keywords:
- __ud2
helpviewer_keywords:
- UD2 instruction
- __ud2 intrinsic
ms.assetid: 0831cd5a-8b65-402e-bb57-11e1d5d7ffd2
ms.openlocfilehash: 2b5f0b9ffec066baa3eb2fa212dfc7baf3a6cb49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333667"
---
# <a name="__ud2"></a>__ud2

**Microsoft 固有の仕様**

未定義の命令を生成します。

## <a name="syntax"></a>構文

```C
void __ud2();
```

## <a name="remarks"></a>解説

定義されていない命令を実行すると、プロセッサは無効なオペコード例外を発生させます。

関数はコンピューター命令と同じであり、 `__ud2` `UD2` カーネルモードでのみ使用できます。 詳細については、 [Intel Corporation](https://software.intel.com/articles/intel-sdm) サイトのドキュメント「Intel Architecture Software Developer's Manual, Volume 2: 命令セットリファレンス」を検索してください。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__ud2`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="example"></a>例

次の例では、未定義の命令を実行して、例外を発生させます。 次に、例外ハンドラーは、リターンコードを0から1に変更します。

```cpp
// __ud2_intrinsic.cpp
#include <stdio.h>
#include <intrin.h>
#include <excpt.h>
// compile with /EHa

int main() {

// Initialize the return code to 0.
int ret = 0;

// Attempt to execute an undefined instruction.
  printf("Before __ud2(). Return code = %d.\n", ret);
  __try {
  __ud2();
  }

// Catch any exceptions and set the return code to 1.
  __except(EXCEPTION_EXECUTE_HANDLER){
  printf("  In the exception handler.\n");
  ret = 1;
  }

// Report the value of the return code.
  printf("After __ud2().  Return code = %d.\n", ret);
  return ret;
}
```

```Output
Before __ud2(). Return code = 0.
  In the exception handler.
After __ud2().  Return code = 1.
```

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
