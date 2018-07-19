---
title: パラメーター配列と省略記号 |Microsoft ドキュメント
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
ms.openlocfilehash: 20d13f327abe3e864007c4941af2ce9fd03ea05d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33158522"
---
# <a name="param-array-and-ellipsis"></a>パラメーター配列と省略記号
オーバー ロードされた関数の呼び出しを解決するためのパラメーター配列の優先順位は、Visual C を c++ マネージ拡張から変更されました。  
  
 マネージ拡張および新しい構文では、c# および Visual Basic のサポートされるパラメーターの配列の明示的なサポートはありません。 代わりに、いずれかのフラグを設定、属性を持つ通常の配列には、次のように。  
  
```  
void Trace1( String* format, [ParamArray]Object* args[] );  
void Trace2( String* format, Object* args[] );  
```  
  
 これら両方の見た目は同じときに、`ParamArray`属性タグこの C# コードまたはその他の CLR 言語の変数に多数の呼び出しのたびに要素の配列として。 マネージ拡張と、新しい構文のプログラムでの動作の変更、オーバー ロードされた関数を 1 つのインスタンスを宣言の省略記号のセットの解決には、2 つ目の宣言、`ParamArray`によって提供される次の例のように、属性Artur laksberg が紹介します。  
  
```  
int fx(...); // 1  
int fx( [ParamArray] Int32[] ); // 2  
```  
  
 マネージ拡張で、省略記号は、属性は、言語の正式な側面ではないために、妥当な属性より優先順位が指定されました。 ただし、新しい構文で param 配列が言語内で直接サポートされていますし、それよりも優先、省略記号がより厳密に型指定するためです。 したがって、次のマネージ拡張で、呼び出しのようになります。  
  
```  
fx( 1, 2 );  
```  
  
 解決される`fx(...)`に解決されるときに、新しい構文で、`ParamArray`インスタンス。 プログラムの動作が経由での省略記号のインスタンスの呼び出しに依存している、 `ParamArray`、署名または呼び出しのいずれかを変更する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [言語の変更の概要 (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)