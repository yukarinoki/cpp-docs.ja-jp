---
description: '詳細情報: 不足している関数本体または変数'
title: 関数本体または変数の未定義
ms.date: 11/04/2016
helpviewer_keywords:
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
ms.openlocfilehash: 6a4349c380fc0f573adc8e372f9e4d2fc3f83873
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155164"
---
# <a name="missing-function-body-or-variable"></a>関数本体または変数の未定義

関数プロトタイプだけを使用すると、コンパイラはエラーを発生させずに続行できますが、関数コードまたは変数空間が予約されていないため、リンカーはアドレスの呼び出しを解決できません。 リンカーが解決する必要がある関数の呼び出しを作成するまで、このエラーは表示されません。

## <a name="example-call-to-an-undefined-function"></a>例: 未定義の関数の呼び出し

Main の関数呼び出しによって LNK2019 が発生します。プロトタイプでは、コンパイラが関数の存在を想定しているからです。  リンカーは、そうでないことを検出します。

```cpp
// LNK2019_MFBV.cpp
// LNK2019 expected
void DoSomething(void);
int main() {
   DoSomething();
}
```

## <a name="example-call-to-an-implemented-function"></a>例: 実装された関数の呼び出し

C++ では、クラス定義のプロトタイプだけでなく、クラスの特定の関数の実装を含めるようにしてください。 ヘッダーファイルの外部でクラスを定義する場合は、関数の前にクラス名を含めるようにしてください ( `Classname::memberfunction` )。

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

## <a name="see-also"></a>関連項目

[リンカツールエラー LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
