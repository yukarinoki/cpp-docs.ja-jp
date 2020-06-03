---
title: noreturn
ms.date: 11/04/2016
f1_keywords:
- noreturn_cpp
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
ms.openlocfilehash: a30840aa0556a7324ba24c0f2aaec57dea88d082
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367865"
---
# <a name="noreturn"></a>noreturn

**マイクロソフト固有**

この **__declspec**属性は、関数が返さないことをコンパイラに通知します。 結果として、コンパイラは **、__declspec(noreturn)** 関数の呼び出し後のコードに到達できないことが認識されます。

コンパイラで値を返さないコントロール パスの関数が検出されると、警告 (C4715) またはエラー メッセージ (C2202) が生成されます。 制御パスが戻らない関数が原因で到達できない場合は **、__declspec(noreturn) を**使用してこの警告またはエラーを回避できます。

> [!NOTE]
> 返される関数に **__declspec(noreturn)を**追加すると、未定義の動作が発生する可能性があります。

## <a name="example"></a>例

次のサンプルでは **、else**句に return ステートメントは含まれていません。  `fatal` **__declspec(noreturn)** として宣言すると、エラーまたは警告メッセージが表示されなくなります。

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

**エンド マイクロソフト 固有**

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)<br/>
[Keywords](../cpp/keywords-cpp.md)
