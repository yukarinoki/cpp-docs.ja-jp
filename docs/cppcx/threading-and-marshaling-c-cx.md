---
title: スレッドとマーシャ リング (C + + CX) |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- C4451
helpviewer_keywords:
- threading issues, C++/CX
- agility, C++/CX
- C++/CX, threading issues
ms.assetid: 83e9ca1d-5107-4194-ae6f-e01bd928c614
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 60d96b46caea15b46e0d6300733efddb98a1b4da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="threading-and-marshaling-ccx"></a>スレッドとマーシャリング (C++/CX)
ほとんどの場合に、標準の C++ オブジェクトと同様に、Windows ランタイム クラスのインスタンスを任意のスレッドからアクセスできます。 このようなクラスを "アジャイル" と呼びます。 ただし、Windows に付属する Windows ランタイム クラスの数が少ないが非アジャイルであり、必要があります使用する標準の C++ オブジェクトよりも COM オブジェクトと同様にします。 非アジャイル クラスを使用するために COM の専門家になる必要はありませんが、クラスのスレッド モデルとマーシャリング動作を考慮する必要があります。 この技術情報では、非アジャイル クラスのインスタンスを使用する必要があるまれなシナリオの背景について説明し、ガイダンスを示します。  
  
## <a name="threading-model-and-marshaling-behavior"></a>スレッド モデルとマーシャリング動作  
 適用される 2 つの属性が示すように、Windows ランタイム クラスは、さまざまな方法で同時実行スレッド アクセスをサポートできます。  
  
-   `ThreadingModel` 属性には、 `ThreadingModel` 列挙体によって定義された STA、MTA、Both のいずれかの値を指定できます。  
  
-   `MarshallingBehavior` 属性には、 `MarshallingType` 列挙体によって定義された Agile、None、Standard のいずれかの値を指定できます。  
  
 `ThreadingModel` 属性では、クラスをアクティブにしたときに読み込む場所を指定します。クラスの読み込み先として、ユーザー インターフェイス スレッド (STA) コンテキストのみ、バックグラウンド スレッド (MTA) コンテキストのみ、またはオブジェクトを作成するスレッドのコンテキスト (Both) を指定できます。 `MarshallingBehavior` 属性値は、さまざまなスレッド コンテキストにおけるオブジェクトの動作を指しますが、ほとんどの場合、これらの値を詳しく理解する必要はありません。  Windows API が提供するクラスの約 90 % には、 `ThreadingModel`=Both と `MarshallingType`Agile があります。 これは、低レベルのスレッドの詳細を透過的および効率的に処理できることを意味します。   `ref new` を使用して "agile" クラスを作成する場合、メイン アプリケーションのスレッドまたは 1 つ以上のワーカー スレッドから、そのクラスのメソッドを呼び出せます。  つまり、Windows から提供されたかサード パーティから提供されたかに関係なく、コード内の任意の場所でアジャイル クラスを使用できます。 クラスのスレッド モデルやマーシャリング動作について考慮する必要はありません。  
  
## <a name="consuming-windows-runtime-components"></a>Windows ランタイム コンポーネントの使用  
 ユニバーサル Windows プラットフォーム アプリを作成するときに、両方アジャイル コンポーネントと非アジャイル コンポーネントとやり取りする場合があります。 非アジャイル コンポーネントとやり取りすると、次の警告が表示されることがあります。  
  
### <a name="compiler-warning-when-consuming-non-agile-classes-c4451"></a>非アジャイル クラス (C4451) 使用時のコンパイラの警告  
 さまざまな理由で、一部のクラスはアジャイルにすることができません。 ユーザー インターフェイス スレッドとバックグラウンド スレッドの両方から非アジャイル クラスのインスタンスにアクセスする場合は、実行時の動作が正しいことを注意深く確認する必要があります。 アプリケーション内のグローバル スコープで非アジャイルのランタイム クラスをインスタンス化する場合、またはそれ自体がアジャイルとマーク付けされている ref クラスのクラス メンバーとして非アジャイル型を宣言する場合、Visual C++ コンパイラは警告を発します。  
  
 非アジャイル クラスで扱いが最も簡単なのは、 `ThreadingModel`=Bothおよび `MarshallingType`=Standard が指定されているものです。  これらのクラスをアジャイルにするには、単に `Agile<T>` ヘルパー クラスを使用します。   次の例は、 `Windows::Security::Credentials::UI::CredentialPickerOptions^`型の非アジャイル オブジェクトの宣言、および結果として生成されるコンパイラの警告を示しています。  
  
```  
  
ref class MyOptions  
    {  
    public:  
        property Windows::Security::Credentials::UI::CredentialPickerOptions^ Options  
  
        {  
            Windows::Security::Credentials::UI::CredentialPickerOptions^ get()   
            {  
                return _myOptions;  
            }  
        }  
    private:  
        Windows::Security::Credentials::UI::CredentialPickerOptions^ _myOptions;  
    };  
```  
  
 次の警告が出されます。  
  
> `Warning 1 warning C4451: 'Platform::Agile<T>::_object' : Usage of ref class 'Windows::Security::Credentials::UI::CredentialPickerOptions' inside this context can lead to invalid marshaling of object across contexts. Consider using 'Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions>' instead`  
  
 マーシャリング動作が「標準」のオブジェクトへの参照を (メンバー スコープまたはグローバル スコープで) 追加する場合、コンパイラは、`Platform::Agile<T>` で型をラップするように勧める警告を発行します。`Consider using 'Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions>' instead``Agile<T>` を使用すると、他のすべてのアジャイル クラスと同じようにクラスを使用できます。 次のような状況では、 `Platform::Agile<T>` を使用します。  
  
-   非アジャイル変数は、グローバル スコープで宣言されます。  
  
-   非アジャイル変数はクラス スコープで宣言されます。使用コードが、ポインターを忍び込ませる、つまり、正しいマーシャリングなしで別のアパートメントで使用する可能性があります。  
  
 このどちらの状況にも該当しない場合は、含んでいるクラスを非アジャイルとしてマークできます。 言い換えれば、直接、非アジャイル クラスでのみ非アジャイル オブジェクトを保持してください platform::agile を使用して非アジャイル オブジェクトを保持\<T > アジャイル クラスでします。  
  
 次の例は、警告を安全に無視できるように、 `Agile<T>` を使用する方法を示しています。  
  
```  
  
#include <agile.h>  
ref class MyOptions  
    {  
    public:  
        property Windows::Security::Credentials::UI::CredentialPickerOptions^ Options  
  
        {  
            Windows::Security::Credentials::UI::CredentialPickerOptions^ get()   
            {  
                return m_myOptions.Get();  
            }  
        }  
    private:  
        Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions^> m_myOptions;  
  
    };  
  
```  
  
 `Agile` を ref クラスの戻り値またはパラメーターとして渡すことはできません。 `Agile<T>::Get()` メソッドは、パブリック メソッドまたはプロパティでアプリケーション バイナリ インターフェイス (ABI) 間で渡せるオブジェクトへのハンドル (^) を返します。  
  
 Visual c では"None"、マーシャ リング動作がインプロセス Windows ランタイム クラスへの参照を作成するときに、コンパイラ警告 c4451 を発行しますが、使用を検討すること`Platform::Agile<T>`です。  コンパイラは、この警告を超えるヘルプを提供できます。従って、クラスを正しく使用して、コードがユーザー インターフェイス スレッドからのみ STA コンポーネントを呼び出すこと、およびバックグラウンド スレッドからのみ MTA コンポーネントを呼び出すことを確認するのはユーザーの責任になります。  
  
## <a name="authoring-agile-windows-runtime-components"></a>アジャイルの Windows ランタイム コンポーネントの作成  
 C + の ref クラスを定義するときに + CX は既定でアジャイル — はその`ThreadingModel`= Both と`MarshallingType`アジャイルを = です。  [!INCLUDE[cppwrl](../cppcx/includes/cppwrl-md.md)]を使用する場合は、 `FtmBase`を使用する `FreeThreadedMarshaller`から派生することで、クラスをアジャイルにできます。  `ThreadingModel`=Both または `ThreadingModel`=MTA が指定されたクラスを作成する場合、クラスがスレッドセーフであることを確認します。 詳細については、「 [オブジェクト (WRL) の作成と利用](http://msdn.microsoft.com/en-us/d5e42216-e888-4f1f-865a-b5ccd0def73e)」を参照してください。  
  
 ref クラスのスレッド モデルとマーシャリングの動作を変更できます。 ただし、クラスを非アジャイルにする変更を加えた場合は、その変更に関連付けられた影響を理解する必要があります。  
  
 次の例は、適用する方法を示しています。`MarshalingBehavior`と`ThreadingModel`ランタイム クラスに、Windows ランタイム クラス ライブラリ内の属性です。 アプリケーションが DLL を使用し、 `ref new` キーワードを使用して `MySTAClass` クラス オブジェクトをアクティベートする場合、オブジェクトはシングル スレッド アパートメントでアクティベートされ、マーシャリングをサポートしません。  
  
```  
using namespace Windows::Foundation::Metadata;  
using namespace Platform;  
  
[Threading(ThreadingModel::STA)]  
[MarshalingBehavior(MarshalingType::None)]   
public ref class MySTAClass  
{  
};  
  
```  
 
 シールされていないクラスでは、マーシャリング属性とスレッド属性が設定されている必要があります。これにより、コンパイラは派生クラスでこれらの属性の値が同じであることを検証できます。 クラスでこれらの属性が明示的に設定されていない場合、コンパイラはエラーを生成し、コンパイルは失敗します。 次のいずれかの場合、シールされていないクラスから派生したクラスでコンパイラ エラーが生成されます。  
  
-   `ThreadingModel` および `MarshallingBehavior` 属性が派生クラスで定義されていない。  
  
-   派生クラスの `ThreadingModel` と `MarshallingBehavior` 属性の値が基底クラスの値と一致しない。  
  
 スレッドとマーシャ リングのサードパーティの Windows ランタイム コンポーネントで必要とされる情報は、コンポーネントのアプリケーション マニフェスト登録情報で指定されます。 作成することのすべての Windows ランタイム コンポーネントのアジャイルことをお勧めします。 これにより、クライアント コードはアプリケーション内の任意のスレッドからコンポーネントを呼び出すことができます。また、それらの呼び出しは、マーシャリングがない直接呼び出しであるため、呼び出しのパフォーマンスが向上します。 この方法でクラスを作成する場合、クラスを使用するために、クライアント コードで `Platform::Agile<T>` を使用する必要はありません。  
  
## <a name="see-also"></a>関連項目  
 [ThreadingModel](http://msdn.microsoft.com/library/windows/apps/xaml/windows.foundation.metadata.threadingmodel.aspx)   
 [MarshallingBehavior](http://msdn.microsoft.com/library/windows/apps/xaml/windows.foundation.metadata.marshalingbehaviorattribute.aspx)