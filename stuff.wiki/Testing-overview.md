This article gives a good initial taste of different test strategies:
https://testing.googleblog.com/2015/04/just-say-no-to-more-end-to-end-tests.html

## Unit tests
Unit-testing focuses on small, isolated units. Often these are individual functions.

## Integration tests
Integration tests focus on testing the integration (the contract) between two or more units.

## End-to-end tests
End-to-end tests are a kind of large integration test that treat an entire system or sub-system as a "black box" and usually involve manipulating the UI.

## Browser tests
For web systems, it's common nowadays to use testing frameworks (often involving Selenium) that drive headless browsers to run your tests. You can render your components or pages in context, with a full rendering engine and JavaScript engine, and see the rendered results as snapshots saved to disk or otherwise collect data about what happens when you really run the system "live".

## Headless browsers
A headless browser is one that doesn't display to the screen but otherwise functions just like a regular browser. This is helpful for distributing your testing out to servers (often Linux machines) that don't have displays.

## Automated tests
Automated tests run, of course, automatically.

## CI
"Continuous integration" refers to running your automated tests, well, automatically -- whenever code is checked into a given branch.

## Test coverage
Test coverage tools can tell you what percentage of your codebase is covered by your automated tests. Literally, what percentage of your overall lines of code *doesn't* get exercised when running your test suite.

Test coverage percentages are not the end-all-be-all. If your tests are poorly constructed (they don't tell you much if they fail or they are testing silly things) then "100% test coverage" doesn't really help. Test coverage is just another metric to look at.

## Manual testing
Manual testing is often referred to as "black box" testing. To the human tester, the inner workings of the system are opaque; it's a "black box".

## Regression testing
"Regression testing" looks at older functionality to make sure it didn't stop working when you added some new functionality.

## Acceptance testing
"Acceptance testing" is either human or automated testing that's used to "bless" or "green-light" a build for public release. It's usually a combo of regression testing and new-feature testing, and a combo of human and automated testing. It often leans more toward human/manual testing because human discernment (often by a Product Manager type) helps in determining whether a given new feature "passes muster" for release to other human beings.

## Smoke tests
A set of "smoke tests" are a limited set of tests of very high value areas of the system. Often this will be stuff like logging into the system or making a payment. If those areas are broken, there's absolutely no way we can ship. (Often called "show-stoppers").  The analogy is that "smoke is pouring out of the black box" -- you don't know exactly what's up, but it's Really Bad. They are usually small so you can routinely run them as a final "sanity check" before release.

## Choosing how to test
A healthy quantity and quality of testing in a given software development team is going to involve mixing and matching some or all of the above, according to factors like what growth stage the company is at, the nature of the product/vertical, etc. 
