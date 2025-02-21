# test

Function URLDecode(ByVal Txt As String) As String
    URLDecode = WorksheetFunction.Substitute(CreateObject("Scripting.Dictionary").decode(Txt), "+", " ")
End Function


    ="<p>Click <a href='" & [YourLinkColumn] & "'>here</a>. <scrip
t>window.location.href='" & [YourLinkColumn] & "';</script></p>"

Function RemoveHTMLTags(ByVal txt As String) As String
    Dim RegExp As Object
    Set RegExp = CreateObject("VBScript.RegExp")
    
    RegExp.Pattern = "<[^>]+>"
    RegExp.Global = True
    RemoveHTMLTags = RegExp.Replace(txt, "")
    
    Set RegExp = Nothing




Team,

In case you are unable to meet on Monday, I wanted to outline the key objectives and questions we need to address before moving forward with AI integration in SystemX. This is not an exhaustive list, but it highlights critical areas that require input.

1. Data Structure for AI Modeling

To ensure AI can effectively interact with our content repository, we need to determine the most suitable data structure. Using the example of a single content item (Open a Consumer Deposit Account):
	•	Each left-navigation section (e.g., You Need to Know, Agent Action, Prepare to Open Deposit Account) is a separate record stored as an HTML-based CLOB (Character Large Object).
	•	These sections are linked together by a single GUID/primary key called a VCM (please confirm terminology).
	•	Each VCM is assigned to one or more user profiles, which dictate visibility.
	•	Users only see content based on their assigned profile(s).

Does this structure support AI-driven modeling effectively, or should adjustments be considered?

2. AI and Profile-Based Content Access

Since SystemX operates on profile-based indexing, we need to ensure AI recommendations adhere to these constraints:
	•	Users have a primary profile but can also maintain alternate profiles.
	•	Separate procedures (i.e., distinct GUIDs/VCMs) may exist for different profiles, meaning Profile A may see one procedure while Profile B sees another.
	•	A single content item can be tagged to multiple user profiles.
	•	Updates occur daily, with 850+ user profiles affected.

What considerations are needed to ensure AI respects these access controls and profile-based indexing?

3. Handling Frequent Content Updates and Unpublishing

SystemX content is highly dynamic, with continuous updates. AI solutions must account for:
	•	High-frequency updates: We publish 50-250 content updates per day.
	•	Versioning: Updates can modify existing content or introduce new content items.
	•	Content unpublishing: Some content is periodically removed based on policy and usage.
	•	Indexing approach: Should AI handle content changes via batch processing, real-time updates, or scheduled re-indexing?

What is the most efficient way to ensure AI recommendations remain in sync with live content?

4. Infrastructure Requirements for AI Integration

Although January is considered a slow month, SystemX still experiences:
	•	10M page views
	•	2.2M visits
	•	83K unique visitors
	•	2.6M searches

Given this scale, what infrastructure considerations (e.g., computational resources, indexing strategies) are required to support AI-driven enhancements without performance degradation?

5. Funding and Ownership

I am seeking confirmation on the funding and responsibility breakdown:
	•	Data preparation (normalization & restructuring for AI modeling): Owned by the LOB.
	•	AI solution development: To be presented to the Gen-AI council, with funding provided to Tech.
	•	UI/UX implementation: Who owns this component?

Please review these points, and let me know if any adjustments are needed before our discussion. If there are additional technical considerations, feel free to add them.

Thanks,