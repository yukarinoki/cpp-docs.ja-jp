---
description: 詳細については、「コンパイラエラー C2338」を参照してください。
title: コンパイラ エラー C2338
ms.date: 11/04/2016
f1_keywords:
- C2338
helpviewer_keywords:
- C2338
ms.assetid: 49bba575-1de4-4963-86c6-ce3226a2ba51
ms.openlocfilehash: 7bbbc7fd6240fce2def470a0d16aa0dba152a109
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234801"
---
# <a name="compiler-error-c2338"></a>コンパイラ エラー C2338

> *エラー メッセージ*

このエラーは、コンパイル中にエラーが発生した場合に発生する可能性があり **`static_assert`** ます。 このメッセージは、パラメーターによって指定され **`static_assert`** ます。

このエラーメッセージは、外部プロバイダーによってコンパイラに生成されることもあります。 ほとんどの場合、これらのエラーは、ATLPROV などの属性プロバイダーの DLL によって報告されます。 このメッセージの一般的な形式は次のとおりです。

- '*attribute*' Atl 属性プロバイダー: エラー atl *数値**メッセージ*

- 属性 '*attribute*' の使用法が正しくありません

- '*usage*': 属性 ' usage ' の形式が正しくありません

多くの場合、これらのエラーは回復不能であり、その後に致命的なコンパイラエラーが発生する可能性があります。

これらの問題を修正するには、属性の使用法を修正します。 たとえば、属性パラメーターを使用する前に宣言する必要がある場合があります。 ATL エラー番号が指定されている場合は、そのエラーのドキュメントで詳細情報を確認してください。
