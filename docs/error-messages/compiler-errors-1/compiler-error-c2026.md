---
title: コンパイラ エラー C2026 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2026
dev_langs:
- C++
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 055ac47d036a1027817aa6b3433bfe0e2e88570e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019550"
---
# <a name="compiler-error-c2026"></a>コンパイラ エラー C2026

文字列が大きすぎるため、末尾の文字は切り捨てられます

文字列で 16380 1 バイト文字の制限を超えていました。

隣接する文字列が連結されている、前に文字列をで 16380 1 バイト文字より長くすることはできません。

この長さが約半分の Unicode 文字列もこのエラーを生成します。

次のように定義された文字列があれば、C2026 が生成されます。

```
char sz[] =
"\
imagine a really, really \
long string here\
";
```

分割できますとおり。

```
char sz[] =
"\
imagine a really, really "
"long string here\
";
```

カスタム リソースまたは外部ファイル内に非常に大きい文字列リテラル (32 K 以上) を保存することがあります。 参照してください[新しいカスタム リソースまたはデータ リソースを作成する](../../windows/creating-a-new-custom-or-data-resource.md)詳細についてはします。