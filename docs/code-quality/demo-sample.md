---
title: コード分析のためのサンプル C++ プロジェクト
description: Visual Studio の Microsoft C++ のコード分析チュートリアルで使用するサンプル ソリューションを作成する方法について説明します。
ms.date: 04/14/2020
ms.topic: sample
helpviewer_keywords:
- demo sample [Visual Studio ALM]
- code analysis, samples
ms.assetid: 09e1b9f7-5916-4ed6-a001-5c2d7e710682
ms.openlocfilehash: c2a1b8c80b7e7aebd1f1530c66ade5859b392028
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372055"
---
# <a name="sample-c-project-for-code-analysis"></a>コード分析のためのサンプル C++ プロジェクト

次の手順では、「[チュートリアル: C/C++ コードの欠陥の分析](../code-quality/walkthrough-analyzing-c-cpp-code-for-defects.md)」のサンプルを作成する方法を示します。 この手順で次が作成されます。

- *CppDemo*という名前の Visual Studio ソリューション。

- *CodeDefects*という名前の静的ライブラリ プロジェクト。

- *アノテーション*という名前の静的ライブラリ プロジェクト。

この手順では、スタティック ライブラリのヘッダー ファイルと *.cpp* ファイルのコードも作成されます。

## <a name="create-the-cppdemo-solution-and-the-codedefects-project"></a>CppDemo ソリューションと CodeDefects プロジェクトを作成する

::: moniker range=">=vs-2019"

1. Visual Studio を開き、[**新しいプロジェクトの作成**] を選択します。

1. [**新しいプロジェクトの作成**] ダイアログで、言語フィルターを**C++** に変更します。

1. [Windows**デスクトップ ウィザード] を**選択し、[**次へ**] をクリックします。

1. [**新しいプロジェクトの構成]** ページの [**プロジェクト名**] テキスト ボックスに *、「CodeDefects」* と入力します。

1. [**ソリューション名**] テキスト ボックスに *「CppDemo」* と入力します。

1. **[作成]** を選択します。

1. Windows**デスクトップ プロジェクト**ダイアログで、[**アプリケーションの種類] を** **[静的ライブラリ (.lib)]** に変更します。

1. **[追加のオプション]** の **[空のプロジェクト]** を選択します。

1. **[OK] を**選択して、ソリューションとプロジェクトを作成します。

::: moniker-end

::: moniker range="vs-2017"

1. Visual Studio を開きます。 メニュー バーで、[**ファイル] を** > クリックして **[新しい** > **プロジェクト**] をクリックします。

1. [**新しいプロジェクト**] ダイアログ で **、[Visual C++** > **Windows デスクトップ**] を選択します。

1. [Windows**デスクトップ ウィザード]** を選択します。

1. [**名前]** ボックスに「*コードの欠陥*」と入力します。

1. [**ソリューション名**] テキスト ボックスに *「CppDemo」* と入力します。

1. **[OK] をクリック**します。

1. Windows**デスクトップ プロジェクト**ダイアログで、[**アプリケーションの種類] を** **[静的ライブラリ (.lib)]** に変更します。

1. **[追加のオプション]** の **[空のプロジェクト]** を選択します。

1. **[OK] を**選択して、ソリューションとプロジェクトを作成します。

::: moniker-end

::: moniker range="vs-2015"

1. Visual Studio を開きます。 メニュー バーで、[**ファイル] を** > クリックして **[新しい** > **プロジェクト**] をクリックします。

1. [**新しいプロジェクト**] ダイアログで、[**テンプレート**> **Visual C++** > **Win32]** を選択します。

1. **[Win32 コンソール アプリケーション]** を選択します。

1. [**名前]** ボックスに「*コードの欠陥*」と入力します。

1. [**ソリューション名**] テキスト ボックスに *「CppDemo」* と入力します。

1. **[OK] をクリック**します。

1. **[Win32 アプリケーション ウィザード]** ダイアログで、[**次へ**] をクリックします。

1. アプリケーションの**種類**を **[静的ライブラリ**] に変更します。

1. [**追加オプション**] で [**プリコンパイル済みヘッダー**] の選択を解除します。

1. [**完了] を**選択して、ソリューションとプロジェクトを作成します。

::: moniker-end

## <a name="add-the-header-and-source-file-to-the-codedefects-project"></a>CodeDefects プロジェクトにヘッダーとソース ファイルを追加する

1. ソリューション エクスプローラで、[**コードの欠陥]** を展開します。

1. 右クリックして、**ヘッダファイル**のコンテキストメニューを開きます。 [ **Add** > **新しい項目の追加 ] を選択**します。

1. [**新しい項目の追加**] ダイアログ ボックスで **、[Visual C++** > **コード**] をクリックし、[ヘッダー**ファイル (.h)]** を選択します。

1. [**名前]** ボックスに *「Bug.h」* と入力し、[**追加**] をクリックします。

1. *Bug.h*の編集ウィンドウで、内容を選択して削除します。

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

1. ソリューション エクスプローラーで右クリックして、**ソース ファイル**のコンテキスト メニューを開きます。 [ **Add** > **新しい項目の追加 ] を選択**します。

1. **[新しい項目の追加]** ダイアログ ボックスで、 **[C++ ファイル (.cpp)]** をクリックします。

1. **[名前]** ボックスに *「Bug.cpp」* と入力し、[**追加**] をクリックします。

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

1. メニュー バーで、[**ファイル] を** > **クリックします。**

## <a name="add-the-annotations-project-and-configure-it-as-a-static-library"></a>Annotations プロジェクトを追加し、それをスタティック ライブラリとして構成する

::: moniker range=">=vs-2019"

1. ソリューション エクスプローラーで**CppDemo**を右クリックし、コンテキスト メニューを開きます。 [**新しいプロジェクトの****追加 ]** > を選択します。

1. [**新しいプロジェクトの追加**] ダイアログ ボックスで **、[Windows デスクトップ ウィザード**] を選択し、[**次へ**] をクリックします。

1. [**新しいプロジェクトの構成]** ページの [**プロジェクト名**] テキスト ボックスに *「注釈*」と入力し、[**作成**] を選択します。

1. Windows**デスクトップ プロジェクト**ダイアログで、[**アプリケーションの種類] を** **[静的ライブラリ (.lib)]** に変更します。

1. **[追加のオプション]** の **[空のプロジェクト]** を選択します。

1. **[OK] を**選択してプロジェクトを作成します。

::: moniker-end

::: moniker range="vs-2017"

1. ソリューション エクスプローラーで**CppDemo**を右クリックし、コンテキスト メニューを開きます。 [**新しいプロジェクトの****追加 ]** > を選択します。

1. [**新しいプロジェクトの追加**] ダイアログで **、[Visual C++** > **Windows デスクトップ**] を選択します。

1. [Windows**デスクトップ ウィザード]** を選択します。

1. [**名前]** テキスト ボックスに *「コメント*」と入力し **、[OK]** をクリックします。

1. Windows**デスクトップ プロジェクト**ダイアログで、[**アプリケーションの種類] を** **[静的ライブラリ (.lib)]** に変更します。

1. **[追加のオプション]** の **[空のプロジェクト]** を選択します。

1. **[OK] を**選択してプロジェクトを作成します。

::: moniker-end

::: moniker range="vs-2015"

1. ソリューション エクスプローラーで**CppDemo**を右クリックし、コンテキスト メニューを開きます。 [**新しいプロジェクトの****追加 ]** > を選択します。

1. [**新しいプロジェクトの追加**] ダイアログボックスで **、[Visual C++** > **Win32]** を選択します。

1. **[Win32 コンソール アプリケーション]** を選択します。

1. [**名前]** テキスト ボックスに「注釈」と入力*します*。

1. **[OK] をクリック**します。

1. **[Win32 アプリケーション ウィザード]** ダイアログで、[**次へ**] をクリックします。

1. アプリケーションの**種類**を **[静的ライブラリ**] に変更します。

1. [**追加オプション**] で [**プリコンパイル済みヘッダー**] の選択を解除します。

1. [**完了] を**選択してプロジェクトを作成します。

::: moniker-end

## <a name="add-the-header-file-and-source-file-to-the-annotations-project"></a>ヘッダー ファイルとソース ファイルを注釈プロジェクトに追加する

1. ソリューション エクスプローラーで、[**注釈**] を展開します。

1. 右クリックして、[**ヘッダ ファイル]** の [**アノテーション**] のコンテキスト メニューを開きます。 [ **Add** > **新しい項目の追加 ] を選択**します。

1. [**新しい項目の追加**] ダイアログ ボックスで **、[Visual C++** > **コード**] をクリックし、[ヘッダー**ファイル (.h)]** を選択します。

1. [**名前]** ボックスに *「annotations.h」と*入力し、[**追加**] をクリックします。

1. *コメント*の編集ウィンドウで、内容を選択して削除します。

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

1. ソリューション エクスプローラーで右クリックし、**ソース ファイル**の [注釈] のコンテキスト メニュー**を**開きます。 [ **Add** > **新しい項目の追加 ] を選択**します。

1. **[新しい項目の追加]** ダイアログ ボックスで、 **[C++ ファイル (.cpp)]** をクリックします。

1. **[名前]** 編集ボックスに *「annotations.cpp」* と入力し、[**追加**] ボタンをクリックします。

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

1. メニュー バーで、[**ファイル] を** > **クリックします。**

これでソリューションが完成し、エラーなしでビルドされるはずです。

::: moniker range="vs-2017"

> [!NOTE]
> Visual Studio 2017 では、IntelliSense`E1097 unknown attribute "no_init_all"`エンジンにスプリアス警告が表示される場合があります。 この警告は無視してかまいません。

::: moniker-end
