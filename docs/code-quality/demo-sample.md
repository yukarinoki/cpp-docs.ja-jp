---
title: コード分析のためのサンプル C++ プロジェクト
description: Visual Studio での Microsoft C++ のコード分析チュートリアルで使用するサンプルソリューションを作成する方法について説明します。
ms.date: 04/14/2020
ms.topic: sample
helpviewer_keywords:
- demo sample [Visual Studio ALM]
- code analysis, samples
ms.assetid: 09e1b9f7-5916-4ed6-a001-5c2d7e710682
ms.openlocfilehash: dd4fe67c05200ccc2865bc7c48b1f5047d77565e
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924626"
---
# <a name="sample-c-project-for-code-analysis"></a>コード分析のためのサンプル C++ プロジェクト

次の手順では、 [「チュートリアル: C/c + + コードを分析して欠陥を分析](../code-quality/walkthrough-analyzing-c-cpp-code-for-defects.md)する」のサンプルを作成する方法について説明します。 この手順で次が作成されます。

- *Cppdemo* という名前の Visual Studio ソリューション。

- *Codedefects* という名前のスタティックライブラリプロジェクト。

- *注釈* という名前のスタティックライブラリプロジェクト。

この手順では、スタティック ライブラリのヘッダー ファイルと *.cpp* ファイルのコードも作成されます。

## <a name="create-the-cppdemo-solution-and-the-codedefects-project"></a>CppDemo ソリューションと CodeDefects プロジェクトを作成する

::: moniker range=">=msvc-160"

1. Visual Studio を開き、[ **新しいプロジェクトの作成** ] を選択します。

1. [ **新しいプロジェクトの作成** ] ダイアログで、言語フィルターを **C++** に変更します。

1. [ **Windows デスクトップウィザード** ] を選択し、[ **次へ** ] をクリックします。

1. [ **新しいプロジェクトの構成** ] ページの [ **プロジェクト名** ] テキストボックスに、「 *codedefects* 」と入力します。

1. [ **ソリューション名** ] テキストボックスに、「 *cppdemo* 」と入力します。

1. **[作成]** を選択します。

1. [ **Windows デスクトッププロジェクト** ] ダイアログボックスで、 **アプリケーションの種類** を [ **スタティックライブラリ (.lib)** ] に変更します。

1. **[追加のオプション]** の **[空のプロジェクト]** を選択します。

1. **[OK]** を選択して、ソリューションとプロジェクトを作成します。

::: moniker-end

::: moniker range="msvc-150"

1. Visual Studio を開きます。 メニュー バーで、 **[ファイル]**  >  **[新規作成]**  >  **[プロジェクト]** を選択します。

1. [ **新しいプロジェクト** ] ダイアログで、[ **Visual C++** > **Windows デスクトップ** ] を選択します。

1. **Windows デスクトップウィザード** を選択します。

1. [ **名前** ] テキストボックスに「 *codedefects* 」と入力します。

1. [ **ソリューション名** ] テキストボックスに、「 *cppdemo* 」と入力します。

1. **[OK]** をクリックします。

1. [ **Windows デスクトッププロジェクト** ] ダイアログボックスで、 **アプリケーションの種類** を [ **スタティックライブラリ (.lib)** ] に変更します。

1. **[追加のオプション]** の **[空のプロジェクト]** を選択します。

1. **[OK]** を選択して、ソリューションとプロジェクトを作成します。

::: moniker-end

::: moniker range="msvc-140"

1. Visual Studio を開きます。 メニュー バーで、 **[ファイル]**  >  **[新規作成]**  >  **[プロジェクト]** を選択します。

1. [ **新しいプロジェクト** ] ダイアログで、[ **テンプレート** > **Visual C++** > **Win32** ] を選択します。

1. [ **Win32 コンソールアプリケーション** ] を選択します。

1. [ **名前** ] テキストボックスに「 *codedefects* 」と入力します。

1. [ **ソリューション名** ] テキストボックスに、「 *cppdemo* 」と入力します。

1. **[OK]** をクリックします。

1. [ **Win32 アプリケーションウィザード** ] ダイアログで、[ **次へ** ] をクリックします。

1. アプリケーションの **種類** を **スタティックライブラリ** に変更します。

1. [ **追加オプション** ] で、 **プリコンパイル済みヘッダー** の選択を解除します。

1. [ **完了** ] を選択して、ソリューションとプロジェクトを作成します。

::: moniker-end

## <a name="add-the-header-and-source-file-to-the-codedefects-project"></a>CodeDefects プロジェクトにヘッダーとソース ファイルを追加する

1. ソリューションエクスプローラーで、[ **Codedefects** ] を展開します。

1. 右クリックして、 **ヘッダーファイル** のコンテキストメニューを開きます。 [ **Add**  >  **新しい項目** の追加] を選択します。

1. [ **新しい項目の追加** ] ダイアログボックスで、[ **Visual C++** コード] を選択し、[  >  **Code****ヘッダーファイル (.h)** ] を選択します。

1. [ **名前** の編集] ボックスに「 *Bug. h* 」と入力し、[ **追加** ] ボタンをクリックします。

1. [ *バグ* の編集] ウィンドウで、内容を選択して削除します。

1. 次のコードをコピーし、エディターで *Bug.h* ファイルに貼り付けます。

    ```cpp
    #pragma once

    #include <windows.h>

    // Function prototypes
    bool CheckDomain(wchar_t const *);
    HRESULT ReadUserAccount();

    // These constants define the common sizes of the
    // user account information throughout the program
    const int USER_ACCOUNT_LEN = 256;
    const int ACCOUNT_DOMAIN_LEN = 128;
    ```

1. ソリューションエクスプローラーで、右クリックして [ **ソースファイル** ] のコンテキストメニューを開きます。 [ **Add**  >  **新しい項目** の追加] を選択します。

1. **[新しい項目の追加]** ダイアログ ボックスで、 **[C++ ファイル (.cpp)]** をクリックします。

1. [ **名前** の編集] ボックスに「 *Bug* 」と入力し、[ **追加** ] ボタンをクリックします。

1. 次のコードをコピーし、エディターで *Bug.cpp* ファイルに貼り付けます。

    ```cpp
    #include "Bug.h"

    // the user account
    wchar_t g_userAccount[USER_ACCOUNT_LEN] = { L"domain\\user" };
    int len = 0;

    bool CheckDomain(wchar_t const* domain)
    {
        return (wcsnlen_s(domain, USER_ACCOUNT_LEN) > 0);
    }

    HRESULT ReadUserAccount()
    {
        return S_OK;
    }

    bool ProcessDomain()
    {
        wchar_t* domain = new wchar_t[ACCOUNT_DOMAIN_LEN];
        // ReadUserAccount gets a 'domain\user' input from
        //the user into the global 'g_userAccount'
        if (ReadUserAccount())
        {
            // Copies part of the string prior to the '\'
            // character onto the 'domain' buffer
            for (len = 0; (len < ACCOUNT_DOMAIN_LEN) && (g_userAccount[len] != L'\0'); len++)
            {
                if (g_userAccount[len] == L'\\')
                {
                    // Stops copying on the domain and user separator ('\')
                    break;
                }
                domain[len] = g_userAccount[len];
            }
            if ((len = ACCOUNT_DOMAIN_LEN) || (g_userAccount[len] != L'\\'))
            {
                // '\' was not found. Invalid domain\user string.
                delete[] domain;
                return false;
            }
            else
            {
                domain[len] = L'\0';
            }
            // Process domain string
            bool result = CheckDomain(domain);

            delete[] domain;
            return result;
        }
        return false;
    }

    int path_dependent(int n)
    {
        int i;
        int j;
        if (n == 0)
            i = 1;
        else
            j = 1;
        return i + j;
    }
    ```

1. メニューバーで、[ **ファイル** ] [  >  **すべて保存** ] の順に選択します。

## <a name="add-the-annotations-project-and-configure-it-as-a-static-library"></a>Annotations プロジェクトを追加し、それをスタティック ライブラリとして構成する

::: moniker range=">=msvc-160"

1. ソリューションエクスプローラーで、[ **Cppdemo** ] を右クリックしてコンテキストメニューを開きます。 [ **Add**  >  **新しいプロジェクト** の追加] を選択します。

1. [ **新しいプロジェクトの追加** ] ダイアログボックスで、[ **Windows デスクトップウィザード** ] を選択し、[ **次へ** ] をクリックします。

1. [ **新しいプロジェクトの構成** ] ページで、[ **プロジェクト名** ] テキストボックスに「 *Annotations* 」と入力し、[ **作成** ] を選択します。

1. [ **Windows デスクトッププロジェクト** ] ダイアログボックスで、 **アプリケーションの種類** を [ **スタティックライブラリ (.lib)** ] に変更します。

1. **[追加のオプション]** の **[空のプロジェクト]** を選択します。

1. **[OK]** を選択して、プロジェクトを作成します。

::: moniker-end

::: moniker range="msvc-150"

1. ソリューションエクスプローラーで、[ **Cppdemo** ] を右クリックしてコンテキストメニューを開きます。 [ **Add**  >  **新しいプロジェクト** の追加] を選択します。

1. [ **新しいプロジェクトの追加** ] ダイアログで、[ **Visual C++** > **Windows デスクトップ** ] を選択します。

1. **Windows デスクトップウィザード** を選択します。

1. [ **名前** ] テキストボックスに「 *Annotations* 」と入力し、[ **OK]** をクリックします。

1. [ **Windows デスクトッププロジェクト** ] ダイアログボックスで、 **アプリケーションの種類** を [ **スタティックライブラリ (.lib)** ] に変更します。

1. **[追加のオプション]** の **[空のプロジェクト]** を選択します。

1. **[OK]** を選択して、プロジェクトを作成します。

::: moniker-end

::: moniker range="msvc-140"

1. ソリューションエクスプローラーで、[ **Cppdemo** ] を右クリックしてコンテキストメニューを開きます。 [ **Add**  >  **新しいプロジェクト** の追加] を選択します。

1. [ **新しいプロジェクトの追加** ] ダイアログで、[ **Visual C++** Win32] を選択し > **Win32** ます。

1. [ **Win32 コンソールアプリケーション** ] を選択します。

1. [ **名前** ] テキストボックスに、「 *Annotations* 」と入力します。

1. **[OK]** をクリックします。

1. [ **Win32 アプリケーションウィザード** ] ダイアログで、[ **次へ** ] をクリックします。

1. アプリケーションの **種類** を **スタティックライブラリ** に変更します。

1. [ **追加オプション** ] で、 **プリコンパイル済みヘッダー** の選択を解除します。

1. **[完了]** を選択して、プロジェクトを作成します。

::: moniker-end

## <a name="add-the-header-file-and-source-file-to-the-annotations-project"></a>ヘッダー ファイルとソース ファイルを注釈プロジェクトに追加する

1. ソリューションエクスプローラーで、[ **注釈** ] を展開します。

1. 右クリックすると、[ **注釈** ] の下の **ヘッダーファイル** のコンテキストメニューが開きます。 [ **Add**  >  **新しい項目** の追加] を選択します。

1. [ **新しい項目の追加** ] ダイアログボックスで、[ **Visual C++** コード] を選択し、[  >  **Code****ヘッダーファイル (.h)** ] を選択します。

1. [ **名前** の編集] ボックスに「 *annotations* 」と入力し、[ **追加** ] ボタンをクリックします。

1. [ *コメント* の編集] ウィンドウで、内容を選択して削除します。

1. 次のコードをコピーし、エディターで *annotations.h* ファイルに貼り付けます。

    ```cpp
    #pragma once
    #include <sal.h>

    struct LinkedList
    {
        struct LinkedList* next;
        int data;
    };

    typedef struct LinkedList LinkedList;

    _Ret_maybenull_ LinkedList* AllocateNode();
    ```

1. ソリューションエクスプローラーで右クリックして、[ **注釈** ] の下にある [ **ソースファイル** ] のコンテキストメニューを開きます。 [ **Add**  >  **新しい項目** の追加] を選択します。

1. **[新しい項目の追加]** ダイアログ ボックスで、 **[C++ ファイル (.cpp)]** をクリックします。

1. [ **名前** の編集] ボックスに「 *annotations* 」と入力し、[ **追加** ] ボタンをクリックします。

1. 次のコードをコピーし、エディターで *annotations.cpp* ファイルに貼り付けます。

    ```cpp
    #include "annotations.h"
    #include <malloc.h>

    _Ret_maybenull_ LinkedList* AllocateNode()
    {
        LinkedList* result = static_cast<LinkedList*>(malloc(sizeof(LinkedList)));
        return result;
    }

    LinkedList* AddTail(LinkedList* node, int value)
    {
        // finds the last node
        while (node->next != nullptr)
        {
            node = node->next;
        }

        // appends the new node
        LinkedList* newNode = AllocateNode();
        newNode->data = value;
        newNode->next = 0;
        node->next = newNode;

        return newNode;
    }
    ```

1. メニューバーで、[ **ファイル** ] [  >  **すべて保存** ] の順に選択します。

これでソリューションが完成し、エラーなしでビルドされるはずです。

::: moniker range="msvc-150"

> [!NOTE]
> Visual Studio 2017 では、IntelliSense エンジンに誤った警告が表示されることがあり `E1097 unknown attribute "no_init_all"` ます。 この警告は無視してかまいません。

::: moniker-end
