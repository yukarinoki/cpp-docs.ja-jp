---
title: deque::deque (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::deque
dev_langs:
- C++
helpviewer_keywords:
- deque member [STL/CLR]
ms.assetid: e5bc9511-619e-469c-b50a-e06858e7fce7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 433b6ff053db0c642c2a81a5765755c9f42e1a0d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="dequedeque-stlclr"></a>deque::deque (STL/CLR)
コンテナー オブジェクトを構築します。  
  
## <a name="syntax"></a>構文  
  
```  
deque();  
deque(deque<Value>% right);  
deque(deque<Value>^ right);  
explicit deque(size_type count);  
deque(size_type count, value_type val);  
template<typename InIt>  
    deque(InIt first, InIt last);  
deque(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `count`  
 挿入する要素の数。  
  
 `first`  
 挿入する範囲の開始しています。  
  
 `last`  
 挿入する範囲の終了。  
  
 `right`  
 挿入するオブジェクトまたは範囲。  
  
 `val`  
 挿入する要素の値です。  
  
## <a name="remarks"></a>コメント  
 : コンス トラクター  
  
 `deque();`  
  
 要素を持たない被制御シーケンスを初期化します。 空の初期被制御シーケンスの指定に使用するとします。  
  
 : コンス トラクター  
  
 `deque(deque<Value>% right);`  
  
 シーケンスに、被制御シーケンスを初期化します。 [`right.begin()`、 `right.end()`)。 Deque オブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスを指定するために使用`right`です。 反復子の詳細については、次を参照してください。 [deque::begin (STL/CLR)](../dotnet/deque-begin-stl-clr.md)と[deque::end (STL/CLR)](../dotnet/deque-end-stl-clr.md)です。  
  
 : コンス トラクター  
  
 `deque(deque<Value>^ right);`  
  
 シーケンスに、被制御シーケンスを初期化します。 [`right->begin()`、 `right->end()`)。 ハンドルがあるの deque オブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスを指定するために使用`right`です。  
  
 : コンス トラクター  
  
 `explicit deque(size_type count);`  
  
 被制御シーケンスを初期化します`count`値を持つ要素各`value_type()`です。 使用する要素をコンテナーを格納するのに既定値を持ちます。  
  
 : コンス トラクター  
  
 `deque(size_type count, value_type val);`  
  
 被制御シーケンスを初期化します`count`値を持つ要素各`val`です。 使用する要素をコンテナーを格納するのに、同じ値を持ちます。  
  
 : コンス トラクター  
  
 `template<typename InIt>`  
  
 `deque(InIt first, InIt last);`  
  
 シーケンスに、被制御シーケンスを初期化します。 [`first`、 `last`)。 これを使用するには、被制御シーケンスの別のシーケンスのコピーを作成します。  
  
 : コンス トラクター  
  
 `deque(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 列挙子によって指定されたシーケンスの被制御シーケンスを初期化します`right`です。 これを使用するには、被制御シーケンスの列挙子によって記述された別のシーケンスのコピーを作成します。  
  
## <a name="example"></a>例  
  
```cpp  
// cliext_deque_construct.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container   
    cliext::deque<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::deque<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::deque<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::deque<wchar_t>::iterator it = c3.end();   
    cliext::deque<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::deque<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::deque<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::deque<wchar_t> c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0  
 x x x x x x  
 x x x x x  
 x x x x x x  
 x x x x x x  
 x x x x x x  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/deque >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::assign (STL/CLR)](../dotnet/deque-assign-stl-clr.md)   
 [deque::generic_container (STL/CLR)](../dotnet/deque-generic-container-stl-clr.md)   
 [operator= (deque) (STL/CLR)](../dotnet/operator-assign-deque-stl-clr.md)