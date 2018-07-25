---
title: '方法: アクティブ化して、WRL を使用して、Windows ランタイム コンポーネントを使用して |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 54828f02-6af3-45d1-b965-d0104442f8d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 50c37438bf3a840f57119245b845d0b94f1873db
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880775"
---
# <a name="how-to-activate-and-use-a-windows-runtime-component-using-wrl"></a>方法: WRL を使用して Windows ランタイム コンポーネントをアクティブ化し使用する
このドキュメントでは、Windows ランタイム C++ テンプレート ライブラリ (WRL) を使用して、Windows ランタイムを初期化する方法とアクティブ化して、Windows ランタイム コンポーネントを使用する方法を示します。  
  
 コンポーネントを使用するには、コンポーネントによって実装されている型へのインターフェイス ポインターを取得する必要があります。 Windows ランタイムの基になるテクノロジは、コンポーネント オブジェクト モデル (COM) であるため、型のインスタンスを維持するために COM 規則が行う必要があります。 たとえば、管理する必要があります、*参照カウント*型がメモリから削除されたときを指定します。  
  
 Windows ランタイムの使用を簡略化には、Windows ランタイム C++ テンプレート ライブラリ テンプレートが用意されて、スマート ポインター、 [ComPtr\<T >](../windows/comptr-class.md)、参照カウントを自動的に実行します。 変数を宣言するとき指定`ComPtr<`*インターフェイス名*`>` *識別子*です。 インターフェイスのメンバーにアクセスするには、識別子に矢印のメンバー アクセス演算子 (`->`) を適用します。  
  
> [!IMPORTANT]
>  インターフェイス関数を呼び出す際は、`HRESULT` の戻り値を必ずテストしてください。  
  
## <a name="activating-and-using-a-windows-runtime-component"></a>Windows ランタイム コンポーネントのアクティブ化と使用  
 次の手順を使用して、`Windows::Foundation::IUriRuntimeClass`アクティベーション ファクトリを Windows ランタイム コンポーネントの作成、そのコンポーネントのインスタンスを作成し、プロパティの値を取得する方法を示すインターフェイスです。 Windows ランタイムを初期化する方法も示します。 完全な例を次に示します。  
  
> [!IMPORTANT]
>  ユニバーサル Windows プラットフォーム (UWP) アプリで Windows ランタイム C++ テンプレート ライブラリを使用すると、通常は、この例は、図のコンソール アプリを使用します。 などの関数`wprintf_s`UWP アプリからは使用できません。 UWP アプリで使用できる関数と型に関する詳細については、次を参照してください。[ユニバーサル Windows プラットフォーム アプリでサポートされない CRT 関数](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)と[Win32 および COM を UWP アプリの](/uwp/win32-and-com/win32-and-com-for-uwp-apps)します。  
  
#### <a name="to-activate-and-use-a-windows-runtime-component"></a>Windows ランタイム コンポーネントをアクティブ化して使用するには  
  
1.  含まれます (`#include`) 必要な Windows ランタイム、Windows ランタイム C++ テンプレート ライブラリ、または C++ 標準ライブラリのヘッダー。  
  
     [!code-cpp[wrl-consume-component#2](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_1.cpp)]  
  
     コードを読みやすくするために、.cpp ファイルでは `using namespace` ディレクティブを使用することをお勧めします。  
  
2.  アプリが実行されるスレッドを初期化します。 すべてのアプリケーションでスレッドとスレッド モデルを初期化する必要があります。 この例では、 [Microsoft::WRL::Wrappers::RoInitializeWrapper](../windows/roinitializewrapper-class.md)クラスを Windows ランタイムを初期化し、指定[RO_INIT_MULTITHREADED](http://msdn.microsoft.com/library/windows/apps/br224661.aspx)スレッド モデルとします。 `RoInitializeWrapper` クラスでは、構築時に `Windows::Foundation::Initialize` を呼び出し、破棄時に `Windows::Foundation::Uninitialize` を呼び出します。  
  
     [!code-cpp[wrl-consume-component#3](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_2.cpp)]  
  
     2 番目のステートメントで、 [RoInitializeWrapper::HRESULT](../windows/roinitializewrapper-hresult-parens-operator.md)演算子を返します、`HRESULT`への呼び出しから`Windows::Foundation::Initialize`です。  
  
3.  作成、*アクティベーション ファクトリ*の`ABI::Windows::Foundation::IUriRuntimeClassFactory`インターフェイスです。  
  
     [!code-cpp[wrl-consume-component#4](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_3.cpp)]  
  
     Windows ランタイムでは、完全修飾名を使用して型を識別します。 `RuntimeClass_Windows_Foundation_Uri`パラメーターは、Windows ランタイムによって提供され、必要なランタイム クラス名を格納する文字列です。  
  
4.  初期化、 [Microsoft::WRL::Wrappers::HString](../windows/hstring-class.md) URI を表す変数`"http://www.microsoft.com"`です。  
  
     [!code-cpp[wrl-consume-component#6](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_4.cpp)]  
  
     Windows ランタイムで、Windows ランタイムで使用される文字列のメモリは割り当てません。 代わりに、Windows ランタイムでは、バッファーを保持し、使用操作については、し作成されたことをバッファーへのハンドルを返しますで、文字列のコピーを作成します。  
  
5.  `IUriRuntimeClassFactory::CreateUri` ファクトリ メソッドを使用して、`ABI::Windows::Foundation::IUriRuntimeClass` オブジェクトを作成します。  
  
     [!code-cpp[wrl-consume-component#7](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_5.cpp)]  
  
6.  `IUriRuntimeClass::get_Domain` メソッドを呼び出し、`Domain` プロパティの値を取得します。  
  
     [!code-cpp[wrl-consume-component#8](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_6.cpp)]  
  
7.  ドメイン名をコンソールに出力して返ります。 すべての `ComPtr` オブジェクトと RAII オブジェクトは自動的にスコープから外れて解放されます。  
  
     [!code-cpp[wrl-consume-component#9](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_7.cpp)]  
  
     [WindowsGetStringRawBuffer](http://msdn.microsoft.com/library/windows/apps/br224636.aspx)関数は、基になる文字列の Unicode 形式の URI を取得します。  
  
 完全な例を次に示します。  
  
 [!code-cpp[wrl-consume-component#1](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_8.cpp)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コードをコンパイルするコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付ける`wrl-consume-component.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe wrl 消費 component.cpp runtimeobject.lib**  
  
## <a name="see-also"></a>関連項目  
 [Windows ランタイム C++ テンプレート ライブラリ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)