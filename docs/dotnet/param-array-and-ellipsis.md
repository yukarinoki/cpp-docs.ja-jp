---
title: パラメーター配列と省略記号 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- function overloading, argument matching
ms.assetid: 492e3f6c-1c4c-4e0c-a358-72f2d39c30be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2caf6415fdbceb506b736e209c6e7e384b567c5a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384378"
---
# <a name="param-array-and-ellipsis"></a>パラメーター配列と省略記号

オーバー ロードされた関数の呼び出しを解決するためのパラメーター配列の優先順位は、Visual c の C++ マネージ拡張から変更されました。

マネージ拡張と、新しい構文の両方で c# および Visual Basic でサポートされるパラメーター配列の明示的なサポートはありません。 代わりに、いずれかのフラグを設定、属性を持つ通常の配列には、次のように。

```
void Trace1( String* format, [ParamArray]Object* args[] );
void Trace2( String* format, Object* args[] );
```

これらは両方ともの見た目は同じときに、`ParamArray`属性これのタグ (C#) またはその他の CLR 言語と、各呼び出しの要素の可変配列として。 マネージ拡張と、新しい構文のプログラムでの動作の変更は、オーバー ロードされた関数がどの 1 つのインスタンスは、省略記号を宣言しますセットの解像度であり、2 つ目の宣言を`ParamArray`によって提供される次の例のように、属性。Artur laksberg が紹介します。

```
int fx(...); // 1
int fx( [ParamArray] Int32[] ); // 2
```

マネージ拡張で、省略記号は、属性は、言語の正式な側面ではないために適切な属性より優先順位が指定されました。 ただし、新しい構文で param 配列が、言語内で直接サポートされています、これよりも優先、省略記号はより厳密に型指定されているため。 したがって、次の管理拡張機能は、呼び出しのようになります。

```
fx( 1, 2 );
```

解決される`fx(...)`に解決する新しい構文で、`ParamArray`インスタンス。 プログラムの動作が経由での省略記号のインスタンスの呼び出し時に依存している、 `ParamArray`、署名または呼び出しのいずれかを変更する必要があります。

## <a name="see-also"></a>関連項目

[言語の変更の概要 (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)