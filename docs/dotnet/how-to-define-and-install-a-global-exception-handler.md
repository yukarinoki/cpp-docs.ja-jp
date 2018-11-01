---
title: '方法: グローバル例外ハンドラーを定義およびインストールする'
ms.date: 11/04/2016
helpviewer_keywords:
- handlers, global
ms.assetid: dd88a812-3bc7-4ce8-8283-4b674c246534
ms.openlocfilehash: 9c6f355bc43fc53d2b8d27a1ee69c059d0f50692
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534538"
---
# <a name="how-to-define-and-install-a-global-exception-handler"></a>方法: グローバル例外ハンドラーを定義およびインストールする

次のコード例に示す方法未処理の例外をキャプチャできます。 フォーム例にはには、ボタンが含まれています。、、押されたときにスローされる例外を発生させる、null 参照を実行します。 この機能は、一般的なコード エラーを表します。 アプリケーション全体の例外ハンドラーがメインの関数によってインストールされている結果の例外をキャッチします。

デリゲートをバインドすることによってこれは、<xref:System.Windows.Forms.Application.ThreadException>イベント。 この場合、後続の例外に送信されますし、`App::OnUnhandled`メソッド。

## <a name="example"></a>例

```
// global_exception_handler.cpp
// compile with: /clr
#using <system.dll>
#using <system.drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Threading;
using namespace System::Drawing;
using namespace System::Windows::Forms;

ref class MyForm : public Form
{
   Button^ b;
public:
   MyForm( )
   {
      b = gcnew Button( );
      b->Text = "Do Null Access";
      b->Size = Drawing::Size(150, 30);
      b->Click += gcnew EventHandler(this, &MyForm::OnClick);
      Controls->Add(b);
   }
   void OnClick(Object^ sender, EventArgs^ args)
   {
      // do something illegal, like call through a null pointer...
      Object^ o = nullptr;
      o->ToString( );
   }
};

ref class App
{
public:
   static void OnUnhandled(Object^ sender, ThreadExceptionEventArgs^ e)
   {
      MessageBox::Show(e->Exception->Message, "Global Exeception");
      Application::ExitThread( );
   }
};

int main()
{
   Application::ThreadException += gcnew
      ThreadExceptionEventHandler(App::OnUnhandled);

   MyForm^ form = gcnew MyForm( );
   Application::Run(form);
}
```

## <a name="see-also"></a>関連項目

[例外処理](../windows/exception-handling-cpp-component-extensions.md)