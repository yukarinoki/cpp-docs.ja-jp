---
title: メンバー関数の概要
ms.date: 11/04/2016
helpviewer_keywords:
- this pointer, and nonstatic member functions
- nonstatic member functions [C++]
- inline functions [C++], treating member functions as
- member functions [C++], definition in class declaration
ms.assetid: 9f77a438-500e-40bb-a6c6-544678f3f4c8
ms.openlocfilehash: d1c3e069325363276e58a617d6ba21cb0b6e4ff0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188468"
---
# <a name="overview-of-member-functions"></a>メンバー関数の概要

メンバー関数は静的か非静的のいずれかになります。 静的メンバー関数には、暗黙的な**この**引数がないため、静的メンバー関数の動作は他のメンバー関数とは異なります。 非静的メンバー関数には**this**ポインターがあります。 メンバー関数は、静的であるないにかかわらず、クラス宣言の内外に定義できます。

メンバー関数がクラス宣言の中で定義されている場合、インライン関数として扱われ、そのクラス名で関数名を修飾する必要はありません。 クラス宣言内で定義された関数は、既にインライン関数として扱われていますが、**インライン**キーワードを使用してコードを記述することもできます。

クラス宣言内で関数を宣言する例を示します。

```cpp
// overview_of_member_functions1.cpp
class Account
{
public:
    // Declare the member function Deposit within the declaration
    //  of class Account.
    double Deposit( double HowMuch )
    {
        balance += HowMuch;
        return balance;
    }
private:
    double balance;
};

int main()
{
}
```

メンバー関数の定義がクラス宣言の外側にある場合は、明示的に**インライン**として宣言されている場合にのみ、インライン関数として扱われます。 また、定義内の関数名はスコープ解決演算子 (`::`) を使用してクラス名で修飾する必要があります。

次の例は、`Account` 関数がクラス宣言の外側で定義されていることを除き、クラス `Deposit` の以前の宣言と同じです。

```cpp
// overview_of_member_functions2.cpp
class Account
{
public:
    // Declare the member function Deposit but do not define it.
    double Deposit( double HowMuch );
private:
    double balance;
};

inline double Account::Deposit( double HowMuch )
{
    balance += HowMuch;
    return balance;
}

int main()
{
}
```

> [!NOTE]
>  メンバー関数がクラス宣言の内部でも個別でも定義できますが、メンバー関数は、クラスが定義された後でクラスに追加することはできません。

メンバー関数を含むクラスは多くの宣言を持つことができますが、メンバー関数自体は 1 つのプログラムに定義を 1 つのみ持つ必要があります。 複数の定義により、リンク時にエラー メッセージが発生します。 クラスにインライン関数定義が含まれている場合、この "1 つの定義" 規則に従うために、関数定義は同じにする必要があります。
