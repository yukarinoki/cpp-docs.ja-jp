---
description: '詳細情報: コンパイラの警告 (レベル 4) C4435'
title: コンパイラの警告 (レベル 4) C4435
ms.date: 11/04/2016
f1_keywords:
- C4435
helpviewer_keywords:
- C4435
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
ms.openlocfilehash: ce5ee4e32f6efa1e7986d55fafa0ceec8b754351
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203511"
---
# <a name="compiler-warning-level-4-c4435"></a>コンパイラの警告 (レベル 4) C4435

'class1': /vd2 下のオブジェクトのレイアウトは仮想ベース 'class2' により変更されます。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

/Vd1 の既定のコンパイルオプションでは、派生クラスには、指定された `vtordisp` 仮想ベースのフィールドがありません。  /Vd2 または `#pragma vtordisp(2)` が有効になっている場合は、オブジェクトのレイアウトを変更する `vtordisp` フィールドが表示されます。  これにより、相互作用モジュールが異なる設定でコンパイルされると、バイナリ互換性の問題が発生する可能性が `vtordisp` あります。

## <a name="example"></a>例

次の例では、C4435 が生成されます。

```cpp
// C4435.cpp
// compile with: /c /W4
#pragma warning(default : 4435)
class A
{
public:
    virtual ~A() {}
};

class B : public virtual A  // C4435
{};
```

## <a name="see-also"></a>関連項目

[vtordisp](../../preprocessor/vtordisp.md)<br/>
[/vd (構築の変位を無効にする)](../../build/reference/vd-disable-construction-displacements.md)
