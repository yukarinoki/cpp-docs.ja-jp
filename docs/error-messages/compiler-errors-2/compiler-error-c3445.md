---
description: 詳細については、「コンパイラエラー C3445」を参照してください。
title: コンパイラエラー C3445
ms.date: 04/10/2017
f1_keywords:
- C3445
helpviewer_keywords:
- C3445
ms.assetid: 0d272bfc-136b-4025-a9ba-5e4eea5f8215
ms.openlocfilehash: 992c0e4f6e8b068bf6c038a6a5f58b45dd80a3c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316037"
---
# <a name="compiler-error-c3445"></a>コンパイラエラー C3445

> '*type*' のコピーリスト初期化では、明示的なコンストラクターを使用できません

ISO C++ 17 標準に従って、コンパイラは、コピーリスト初期化でのオーバーロードの解決に関する明示的なコンストラクターを考慮する必要がありますが、実際にオーバーロードが選択されている場合はエラーを発生させる必要があります。

Visual Studio 2017 以降では、コンパイラは、Visual Studio 2015 で見つからなかった初期化子リストを使用して、オブジェクトの作成に関連するエラーを検出します。 これらのエラーが発生すると、実行時にクラッシュまたは未定義の動作が発生する可能性があります。

## <a name="example"></a>例

次の例では、C3445 が生成されます。

```cpp
// C3445.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1 = { 1 };     // error C3445: copy-list-initialization of
                      //     'A' cannot use an explicit constructor
}
```

エラーを修正するには、代わりに直接初期化を使用します。

```cpp
// C3445b.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1{ 1 };
}
```
