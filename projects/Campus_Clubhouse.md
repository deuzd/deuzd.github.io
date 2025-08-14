---
layout: project
type: project
image: img/CC-home.png
title: "Campus Clubhouse"
date: 2025-08-13
published: true
labels:
  - Website
  - HTML
summary: "Campus Clubhouse was made in order to help students find available clubs at UH Manoa"
---

## Overview
Campus Clubhouse was a project that two other groupmates, Richard and Andy, designed in order to help students find clubs that they may be interested in at UH Manoa. Currently there is no offical website that contains the avaible clubs, though there is a Google spreadsheet that has the registered independent organizations, or RIO's.

When you first enter the website there is a button that will take you to a list of clubs that we used as group data in order to show a variety of different clubs, ranging from the Manoa Scholars to the K-Pop Cardio Crew. You can also create an account which would allow you to better specify your interests, or simply search the club you are looking for. 

![](/img/CC-home.png){: width="600" }

## My Contributions
I was in charge of creating the sample data to use for the websites, so I tried to gather from a wide variety of clubs, in order to showcase the potential flexibility for all of the clubs available. I created a template that was simple to navigate through in order for it to be more user friendly where you can select the club you are interested in and find any important information for it, such as the president or person of charge, any schedules or meeting plans, along with another brief description of what the club entails and how to get started if you wanted to join. I also included a logo of the club and a link to any website or other media involved with the club.

![](/img/CC_clubs.png){: width="600" }

![](/img/CC_8bit.png){: width="600" }

## Template for each club in HTML
```html

'use client';

import Image from 'next/image';
import Link from 'next/link';
import { Container, Row, Col, Card, Badge, Button } from 'react-bootstrap';

export const metadata = {
  title: '8Bit Club · Campus Clubhouse',
  description: 'Mockup club page for 8Bit (UH Mānoa) in the Campus Clubhouse style.',
};

export default function EightBitClubPage() {
  return (
    <main>
      {/* Hero */}
      <section className="bg-light py-5 border-bottom">
        <Container>
          <Row className="align-items-center g-4">
            <Col md={3}>
              <Image
                src="/8bit-logo.png"
                alt="8Bit UH Mānoa Logo"
                width={200}
                height={200}
                className="img-fluid rounded"
              />
            </Col>
            <Col md={9}>
              <div className="d-flex align-items-center gap-2 mb-2">
                <h1 className="m-0">8Bit (UH Mānoa)</h1>
                <Badge bg="success">Technology</Badge>
                <Badge bg="success">Gaming</Badge>
                <Badge bg="success">Community</Badge>
              </div>
              <p className="text-muted mb-3">
                A student community for game development, retro and modern gaming culture,
                creative coding, and tech meetups at UH Mānoa.
              </p>
              <div className="d-flex flex-wrap gap-2">
                {/* External link as <a> */}
                <Button as="a" href="https://8bithawaii.org/" target="_blank" rel="noreferrer">
                  Visit Website
                </Button>

                {/* Internal link wrapped with <Link> */}
                <Link href="/clubs">
                  <Button variant="outline-secondary">← Back to Clubs</Button>
                </Link>
              </div>
            </Col>
          </Row>
        </Container>
      </section>

      {/* Content */}
      <Container className="py-5">
        <Row className="g-4">
          <Col lg={8}>
            {/* About */}
            <Card className="mb-4">
              <Card.Body>
                <Card.Title>About</Card.Title>
                <Card.Text>
                  8Bit brings together UH Mānoa students who love building and playing games,
                  experimenting with interactive media, and learning the tools of the trade—from
                  engines and art pipelines to sound and publishing. We run beginner-friendly
                  workshops, casual game nights, and occasional jams/collabs.
                </Card.Text>
              </Card.Body>
            </Card>

            {/* Upcoming / Regular Meetings */}
            <Card className="mb-4">
              <Card.Body>
                <Card.Title>Meetings & Events</Card.Title>
                <ul className="mb-0">
                  <li>
                    <strong>Getting started:</strong>
                    {' '}
                    To find out more information you can join their Discord server
                    {' '}
                    <a
                      href="https://discord.gg/T7Eu75fpAf"
                      target="_blank"
                      rel="noreferrer"
                      className="link-primary"
                    >
                      here
                    </a>
                    .
                  </li>

                </ul>
              </Card.Body>
            </Card>

            {/* How to Join */}
            <Card className="mb-4">
              <Card.Body>
                <Card.Title>How to Join</Card.Title>
                <ol className="mb-3">
                  <li>Check the website for the next meeting and quick onboarding.</li>
                  <li>Bring a laptop (optional) if you want to follow along during workshops.</li>
                  <li>Say hi! All majors and experience levels are welcome.</li>
                </ol>
                <div className="d-flex flex-wrap gap-2">
                  {/* External link as <a> */}
                  <Button as="a" href="https://8bithawaii.org/" target="_blank" rel="noreferrer">
                    Get Updates
                  </Button>

                  {/* Internal link wrapped with <Link> */}
                  <Link href="/clubs">
                    <Button variant="outline-secondary">Explore More Clubs</Button>
                  </Link>
                </div>
              </Card.Body>
            </Card>
          </Col>

          {/* Sidebar */}
          <Col lg={4}>
            {/* Quick Facts */}
            <Card className="mb-4">
              <Card.Body>
                <Card.Title>Quick Facts</Card.Title>
                <div className="d-flex flex-column gap-2">
                  <div>
                    <div className="text-muted">Campus</div>
                    <div>UH Mānoa</div>
                  </div>
                  <div>
                    <div className="text-muted">Category</div>
                    <div>Tech · Gaming · Community</div>
                  </div>
                  <div>
                    <div className="text-muted">Membership</div>
                    <div>Open to all UH students</div>
                  </div>
                </div>
              </Card.Body>
            </Card>

            {/* Contact */}
            <Card className="mb-4">
              <Card.Body>
                <Card.Title>Contact</Card.Title>
                <p className="mb-3">
                  Have questions or want to collaborate? Please reach out!
                </p>
                <div className="d-flex flex-column gap-2">
                  <Button as="a" href="https://8bithawaii.org/" target="_blank" rel="noreferrer">
                    Website
                  </Button>
                </div>
              </Card.Body>
            </Card>

            {/* Officers (mock data) */}
            <Card>
              <Card.Body>
                <Card.Title>Officers</Card.Title>
                <ul className="mb-0">
                  <li>
                    <strong>Leaders:</strong>
                    {' '}
                    Leighton Miguel, Gabrielle Huliganga
                  </li>
                  <li>
                    <strong>Emails:</strong>
                    {' '}
                    lmig4@hawaii.edu
                  </li>
                  <li>
                    {' '}
                    gabbyhuli808@gmail.com
                  </li>
                </ul>
              </Card.Body>
            </Card>
          </Col>
        </Row>
      </Container>
    </main>
  );
}
```

## What I learned from this experience
I think the biggest thing that I took away from this project was the amount of effort it takes to actually make a running website from basically scratch. During the project we were also asked to take effort estimations, gauging how long we thought each part of the project would take, which I thought was pretty helpful. It helped me better my time management knowing that a certain issue would take a certain amount of time so I had to plan accordingly. Sometimes it took me longer than expected to finish the issue but that just motivates me to become a more time efficient worker.
