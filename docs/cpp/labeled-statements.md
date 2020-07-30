---
title: ラベル付きステートメント
ms.date: 11/04/2016
helpviewer_keywords:
- labeled statement
- statements, labeled
ms.assetid: 456a26d5-0fcc-4d1a-b71f-fa9ff3d73b91
ms.openlocfilehash: a10d071e46c79f49abf7e3eba498fae0487ccdc7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213360"
---
# <a name="labeled-statements"></a>ラベル付きステートメント

ラベルはプログラムの制御を特定のステートメントに直接移動するために使用されます。

```
identifier :  statement
case constant-expression :  statement
default :  statement
```

ラベルのスコープはラベルが宣言されている関数全体です。

## <a name="remarks"></a>解説

次の 3 種類のラベル付きステートメントがあります。 すべての種類で、そのタイプのラベルをステートメントと区切るためにコロンが使用されます。 case ラベルと default ラベルは、case ステートメントに固有です。

```cpp
#include <iostream>
using namespace std;

void test_label(int x) {

    if (x == 1){
        goto label1;
    }
    goto label2;

label1:
    cout << "in label1" << endl;
    return;

label2:
    cout << "in label2" << endl;
    return;
}

int main() {
    test_label(1);  // in label1
    test_label(2);  // in label2
}
```

**GoTo ステートメント**

ソースプログラム内の*識別子*ラベルの外観によってラベルが宣言されます。 [Goto](../cpp/goto-statement-cpp.md)ステートメントのみが*識別子*ラベルに制御を転送できます。 次のコードフラグメントは、 **`goto`** ステートメントと*識別子*ラベルの使用方法を示しています。

ラベルは単独では使用できず、常にステートメントと一緒に使用する必要があります。 ラベルのみが必要な場合は、ラベルの後に null ステートメントを置きます。

ラベルには関数スコープがあるため、同じ関数内で再宣言できません。 ただし、違う関数内に同じ名前をラベルとして使用することはできます。

```cpp
// labels_with_goto.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   using namespace std;
   goto Test2;

   cout << "testing" << endl;

   Test2:
      cerr << "At Test2 label." << endl;
}

//Output: At Test2 label.
```

**Case ステートメント**

キーワードの後に表示されるラベル **`case`** は、ステートメントの外側でも表示できません **`switch`** 。 (この制限は、キーワードにも適用さ **`default`** れます)。次のコードフラグメントは、ラベルの正しい使用方法を示してい **`case`** ます。

```cpp
// Sample Microsoft Windows message processing loop.
switch( msg )
{
   case WM_TIMER:    // Process timer event.
      SetClassWord( hWnd, GCW_HICON, ahIcon[nIcon++] );
      ShowWindow( hWnd, SW_SHOWNA );
      nIcon %= 14;
      Yield();
      break;

   case WM_PAINT:
      memset( &ps, 0x00, sizeof(PAINTSTRUCT) );
      hDC = BeginPaint( hWnd, &ps );
      EndPaint( hWnd, &ps );
      break;

   default:
      // This choice is taken for all messages not specifically
      //  covered by a case statement.

      return DefWindowProc( hWnd, Message, wParam, lParam );
      break;
}
```

## <a name="labels-in-the-case-statement"></a>Case ステートメント内のラベル

キーワードの後に表示されるラベル **`case`** は、ステートメントの外側でも表示できません **`switch`** 。 (この制限は、キーワードにも適用さ **`default`** れます)。次のコードフラグメントは、ラベルの正しい使用方法を示してい **`case`** ます。

```cpp
// Sample Microsoft Windows message processing loop.
switch( msg )
{
   case WM_TIMER:    // Process timer event.
      SetClassWord( hWnd, GCW_HICON, ahIcon[nIcon++] );
      ShowWindow( hWnd, SW_SHOWNA );
      nIcon %= 14;
      Yield();
      break;

   case WM_PAINT:
      // Obtain a handle to the device context.
      // BeginPaint will send WM_ERASEBKGND if appropriate.

      memset( &ps, 0x00, sizeof(PAINTSTRUCT) );
      hDC = BeginPaint( hWnd, &ps );

      // Inform Windows that painting is complete.

      EndPaint( hWnd, &ps );
      break;

   case WM_CLOSE:
      // Close this window and all child windows.

      KillTimer( hWnd, TIMER1 );
      DestroyWindow( hWnd );
      if ( hWnd == hWndMain )
         PostQuitMessage( 0 );  // Quit the application.
      break;

   default:
      // This choice is taken for all messages not specifically
      //  covered by a case statement.

      return DefWindowProc( hWnd, Message, wParam, lParam );
      break;
}
```

## <a name="labels-in-the-goto-statement"></a>GoTo ステートメント内のラベル

ソースプログラム内の*識別子*ラベルの外観によってラベルが宣言されます。 [Goto](../cpp/goto-statement-cpp.md)ステートメントのみが*識別子*ラベルに制御を転送できます。 次のコードフラグメントは、 **`goto`** ステートメントと*識別子*ラベルの使用方法を示しています。

ラベルは単独では使用できず、常にステートメントと一緒に使用する必要があります。 ラベルのみが必要な場合は、ラベルの後に null ステートメントを置きます。

ラベルには関数スコープがあるため、同じ関数内で再宣言できません。 ただし、違う関数内に同じ名前をラベルとして使用することはできます。

```cpp
// labels_with_goto.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   using namespace std;
   goto Test2;

   cout << "testing" << endl;

   Test2:
      cerr << "At Test2 label." << endl;
// At Test2 label.
}
```

## <a name="see-also"></a>関連項目

[C++ ステートメントの概要](../cpp/overview-of-cpp-statements.md)<br/>
[switch ステートメント (C++)](../cpp/switch-statement-cpp.md)
