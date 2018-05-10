---
title: コンパイラ エラー C2558 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2558
dev_langs:
- C++
helpviewer_keywords:
- C2558
ms.assetid: 822b701e-dcae-423a-b21f-47f36aff9c90
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d7db417edebf0a1fff6ef87bf8ae407889a0e0af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2558"></a>コンパイラ エラー C2558
'identifier' : プライベート メンバー、プロテクト メンバーの初期化にはコンストラクターが必要です。  
  
 コピー コンストラクターは、あるオブジェクトを同じ型の別のオブジェクトの値で初期化します。 つまり、オブジェクトのコピーを作成します。コンストラクターを定義しないと、コンパイラは既定のコピー コンストラクターを生成します。  
  
### <a name="to-fix-this-error"></a>このエラーを修復するには  
  
1.  この問題は、コピー コンストラクターが `private` であるクラスをコピーしようとしたときに発生する場合があります。 ほとんどの場合、`private` コピー コンストラクターを持つクラスはコピーできません。 一般的なプログラミング技法では、`private` コピー コンストラクターを宣言してクラスを直接使用しないようにします。 このクラスは、単独では役に立たない、つまり正常に機能させるには別のクラスを必要とする場合があります。  
  
     `private` コピー コンストラクターを持つクラスを使用しても安全であると判断したら、`private` コンストラクターを持つこのクラスから新しいクラスを派生させ、`public` コピー コンストラクターまたは `protected` コピー コンストラクターをその新しいクラスで使用できるようにします。 この派生クラスを元のクラスがあった位置で使用するとエラーを解決できます。  
  
2.  この問題は、コピー コンストラクターが明示的であるクラスをコピーしようとしたときに発生する場合があります。 コピー コンストラクターを `explicit` として宣言すると、関数との間でクラス オブジェクトの受け渡しができなくなります。 明示的なコンス トラクターの詳細については、次を参照してください。[ユーザー定義型の変換](../../cpp/user-defined-type-conversions-cpp.md)です。  
  
3.  この問題は、`const` 参照パラメーターを受け取らないコピー コンストラクターを使用して、`const` と宣言されたクラス インスタンスをコピーしようとしたときに発生する場合があります。 non-const 型参照ではなく、`const` 型参照を使用して、コピー コンストラクターを宣言します。