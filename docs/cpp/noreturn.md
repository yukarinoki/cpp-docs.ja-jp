---
title: noreturn
ms.date: 11/04/2016
f1_keywords:
- noreturn_cpp
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
ms.openlocfilehash: 1d78e8f5116eabf9073205b938156197bf1001a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245246"
---
# <a name="noreturn"></a>noreturn

## <a name="microsoft-specific"></a>Microsoft 固有の仕様

これは、 **_ _declspec**属性は、関数が返されないことをコンパイラに指示します。 その結果、コンパイラで認識されるへの呼び出しの後のコードを **__declspec(noreturn)** 関数に到達できません。

コンパイラで値を返さないコントロール パスの関数が検出されると、警告 (C4715) またはエラー メッセージ (C2202) が生成されます。 関数を返さないためコントロール パスに到達できない場合は使用できます **__declspec(noreturn)** この警告またはエラーを防ぐためです。

> [!NOTE]
>  追加 **__declspec(noreturn)** を返すと予想される関数の未定義の動作に 。

## <a name="example"></a>例

次のサンプルでは、**他**句に return ステートメントが含まれていません。  宣言する`fatal`として **__declspec(noreturn)** エラーまたは警告メッセージを回避できます。

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

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)