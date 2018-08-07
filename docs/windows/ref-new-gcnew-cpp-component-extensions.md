---
title: ref new、gcnew (C++ コンポーネント拡張) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- gcnew
- ref new
- gcnew_cpp
dev_langs:
- C++
helpviewer_keywords:
- ref new keyword (C++)
- gcnew keyword [C++]
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 51aec80ee24d96cf08d55778e108492d16ecfcc9
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606186"
---
# <a name="ref-new-gcnew--c-component-extensions"></a>ref new、gcnew (C++ コンポーネント拡張)
**Ref 新しい**集計キーワードは、ガベージ コレクションのオブジェクトにアクセスできなくなったし、識別するハンドルを返す対象である型のインスタンスを割り当てます ([^](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)) に割り当てられたオブジェクト。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 メモリが割り当てられる型のインスタンスを**ref 新しい**自動的に解放されます。  
  
 A **ref 新しい**操作がスローされます`OutOfMemoryException`メモリを割り当てることがない場合。  
  
 ネイティブ C++ の型のメモリの割り当てし、割り当て解除の方法の詳細については、次を参照してください。[新しい演算子と delete 演算子](../cpp/new-and-delete-operators.md)します。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 使用**ref 新しい**Windows ランタイム オブジェクト有効期間が自動的に管理用のメモリを割り当てられません。 オブジェクトは、参照の最後のコピーがスコープ外になった後で参照カウントが 0 になると、自動的に解放されます。 詳細については、次を参照してください。 [Ref クラスと構造体](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx)します。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: `/ZW`  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
 割り当てられているマネージ型 (参照または値型) のメモリ**gcnew**、ガベージ コレクションを使用して割り当てを解除します。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: `/clr`  
  
### <a name="examples"></a>使用例  
  
 次の例では**gcnew**メッセージ オブジェクトを割り当てます。  
  
```cpp  
// mcppv2_gcnew_1.cpp  
// compile with: /clr  
ref struct Message {  
   System::String^ sender;  
   System::String^ receiver;  
   System::String^ data;  
};  
  
int main() {  
   Message^ h_Message  = gcnew Message;  
  //...  
}  
```  
  
 次の例では**gcnew**参照型のように使用するためのボックス化された値型を作成します。  
  
```cpp  
// example2.cpp : main project file.  
// compile with /clr  
using namespace System;  
value class Boxed {  
    public:  
        int i;  
};  
int main()  
{  
    Boxed^ y = gcnew Boxed;  
    y->i = 32;  
    Console::WriteLine(y->i);  
    return 0;  
}  
```  
  
 **出力**  
  
```Output  
32  
```  
  
## <a name="see-also"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)