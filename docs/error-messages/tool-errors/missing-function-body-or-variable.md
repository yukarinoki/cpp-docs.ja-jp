---
title: 関数本体または変数の未定義
ms.date: 11/04/2016
helpviewer_keywords:
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
ms.openlocfilehash: 6d2ef22b90009d320485fb6fe3f7e308ae05c442
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173622"
---
# <a name="missing-function-body-or-variable"></a>関数本体または変数の未定義

関数プロトタイプだけを使用すると、コンパイラはエラーを発生させずに続行できますが、関数コードまたは変数空間が予約されていないため、リンカーはアドレスの呼び出しを解決できません。 リンカーが解決する必要がある関数の呼び出しを作成するまで、このエラーは表示されません。

## <a name="example"></a>例

Main の関数呼び出しによって LNK2019 が発生します。プロトタイプでは、コンパイラが関数の存在を想定しているからです。  リンカーは、そうでないことを検出します。

```cpp
// LNK2019_MFBV.cpp
// LNK2019 expected
void DoSomething(void);
int main() {
   DoSomething();
}
```

## <a name="example"></a>例

でC++は、クラス定義のプロトタイプだけでなく、クラスに特定の関数の実装を含めるようにしてください。 ヘッダーファイルの外部でクラスを定義する場合は、関数の前にクラス名を含めるようにしてください (`Classname::memberfunction`)。

```cpp
// LNK2019_MFBV_2.cpp
// LNK2019 expected
struct A {
   static void Test();
};

// Should be void A::Test() {}
void Test() {}

int main() {
   A AObject;
   AObject.Test();
}
```

## <a name="see-also"></a>参照

[リンカー ツール エラー LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
