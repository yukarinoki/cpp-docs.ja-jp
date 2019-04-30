---
title: コンパイラ エラー C3495
ms.date: 11/04/2016
f1_keywords:
- C3495
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
ms.openlocfilehash: 3e387fe77c521a4f25ba67205f1fbd552397e272
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62381040"
---
# <a name="compiler-error-c3495"></a>コンパイラ エラー C3495

'var': ラムダ キャプチャには自動ストレージ存続期間が指定されている必要があります

`static` または `extern`とマークされている変数など、自動ストレージ存続期間がない変数をキャプチャすることはできません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- `static` または `extern` 変数をラムダ式のキャプチャ リストに渡さないでください。

## <a name="example"></a>例

次の例では、 `static` 変数 `n` がラムダ式のキャプチャ リストにあるため、C3495 が生成されます。

```
// C3495.cpp

int main()
{
   static int n = 66;
   [&n]() { return n; }(); // C3495
}
```

## <a name="see-also"></a>関連項目

[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)

