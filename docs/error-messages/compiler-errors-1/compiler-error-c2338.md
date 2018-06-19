---
title: コンパイラ エラー C2338 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2338
dev_langs:
- C++
helpviewer_keywords:
- C2338
ms.assetid: 49bba575-1de4-4963-86c6-ce3226a2ba51
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 156074f20517c1d2e2f4fdb4ac5c54d6cf014276
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33222307"
---
# <a name="compiler-error-c2338"></a>コンパイラ エラー C2338  
  
> *エラー メッセージ*  
  
このエラーは、によって発生することができます、`static_assert`コンパイル中にエラー。 によってメッセージが提供される、`static_assert`パラメーター。   
  
このエラー メッセージは、コンパイラに外部プロバイダーによって生成できます。 ほとんどの場合は、これらのエラーは、属性プロバイダー ATLPROV などの DLL によって報告されます。 このメッセージのいくつかの一般的な形式は次のとおりです。

> '*属性*' Atl 属性プロバイダー: エラー ATL*数**メッセージ*  
  
> 属性の使用法が正しくない '*属性*'
  
> '*使用状況*': 属性 'usage' の形式が正しくありません  
  
これらのエラーは、回復することはない多くの場合、され、コンパイラの致命的なエラー続きます。  
  
これらの問題を解決するには、属性の使用方法を修正します。 たとえば、場合によってを使用する前になる属性のパラメーターを宣言する必要があります。 ATL エラー番号を指定する場合より具体的な情報は、このエラーのマニュアルを確認します。  
