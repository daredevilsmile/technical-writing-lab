Exercise C — Technical Report Executive Summary



&#x20;Executive Summary



This evaluation assessed MySQL, PostgreSQL, and MongoDB as potential database platforms for a new university student records management system. The four-week evaluation focused on the system's ability to manage structured student information, including personal details, enrolment records, and grades; support up to 200 concurrent staff users; maintain ACID compliance for data integrity; and remain manageable by a small IT team with limited database expertise.



Based on these requirements, we recommend \*\*PostgreSQL\*\* as the preferred database platform. PostgreSQL provides strong ACID compliance and reliable support for structured relational data, making it well suited to maintaining accurate student records and relationships between enrolment and grade information. It can also support the expected level of concurrent access without requiring a large specialist administration team.



The two most important factors driving this recommendation were \*\*data integrity\*\* and \*\*maintainability\*\*. PostgreSQL provides the transactional reliability required for sensitive academic records while offering a mature, well-documented platform that can be managed by a small IT team. Although MySQL is also a suitable relational option, PostgreSQL provides the strongest overall fit for the university's requirements.

