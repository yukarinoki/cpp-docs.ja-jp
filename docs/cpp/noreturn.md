---
description: '詳細情報: noreturn'
title: noreturn
ms.date: 11/04/2016
f1_keywords:
- noreturn_cpp
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
ms.openlocfilehash: 829f8cc2d81ae1b9f55024442f1a38b495d54896
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195360"
---
# <a name="noreturn"></a>noreturn

**Microsoft 固有の仕様**

この属性は、関数がを **`__declspec`** 返さないことをコンパイラに指示します。 その結果、コンパイラは、関数への呼び出しに続くコードに到達できないことを認識し **`__declspec(noreturn)`** ます。

コンパイラで値を返さないコントロール パスの関数が検出されると、警告 (C4715) またはエラー メッセージ (C2202) が生成されます。 を返さない関数によってコントロールパスに到達できない場合は、を使用して **`__declspec(noreturn)`** この警告またはエラーを回避できます。

> [!NOTE]
> を **`__declspec(noreturn)`** 返すことが想定されている関数にを追加すると、未定義の動作が発生する可能性があります。

## <a name="example"></a>例

次の例では、 **`else`** 句に return ステートメントが含まれていません。  `fatal`としてを宣言 **`__declspec(noreturn)`** すると、エラーまたは警告メッセージが表示されなくなります。

```cpp
// noreturn2.cpp
__declspec(noreturn) extern void fatal () {}

int main() {
   if(1)
     return 1;
   else if(0)
     return 0;
   else
     fatal();
}
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
